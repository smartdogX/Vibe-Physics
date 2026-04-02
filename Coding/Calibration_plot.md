# Calibration

|Sequence|Elementary|Peak channel(s)|Peak energy(MeV)|
|---------|----|------|------|
|1|$^{60}\rm{Co}$|9129/10344|1.173/1.332|
|2|$^{23}\rm{Na}$|4099/9824|0.511/1.275|
|3|$^{137}\rm{Cs}$|5327|0.662|

Prompt: generate a python code to help me plot the calibration of Compton scattering.

## Solution

Note:
- The corrected `^{23}Na` channel for `1.275 MeV` is `9824`.
- All listed calibration points are included in the linear fit.

Saved runnable script: `calibration_plot.py`

```python
from pathlib import Path
import warnings

import matplotlib.pyplot as plt
import numpy as np


POINTS = [
    {"label": "60Co", "channel": 9129, "energy": 1.173, "use_for_fit": True},
    {"label": "60Co", "channel": 10344, "energy": 1.332, "use_for_fit": True},
    {"label": "23Na", "channel": 4099, "energy": 0.511, "use_for_fit": True},
    {"label": "23Na", "channel": 9824, "energy": 1.275, "use_for_fit": True},
    {"label": "137Cs", "channel": 5327, "energy": 0.662, "use_for_fit": True},
]


def warn_on_duplicate_channels(points, energy_tolerance=1e-6):
    grouped = {}
    for point in points:
        grouped.setdefault(point["channel"], []).append(point["energy"])

    for channel, energies in grouped.items():
        unique_energies = sorted(set(energies))
        if len(unique_energies) > 1 and max(unique_energies) - min(unique_energies) > energy_tolerance:
            warnings.warn(
                f"Channel {channel} appears with conflicting energies: {unique_energies}. "
                "The fit will use only the points marked use_for_fit=True.",
                stacklevel=2,
            )


def linear_fit(points):
    fit_points = [point for point in points if point["use_for_fit"]]
    channels = np.array([point["channel"] for point in fit_points], dtype=float)
    energies = np.array([point["energy"] for point in fit_points], dtype=float)

    slope, intercept = np.polyfit(channels, energies, 1)
    predicted = slope * channels + intercept
    ss_res = np.sum((energies - predicted) ** 2)
    ss_tot = np.sum((energies - np.mean(energies)) ** 2)
    r_squared = 1.0 - ss_res / ss_tot if ss_tot > 0 else 1.0
    return slope, intercept, r_squared


def make_plot(points, output_path):
    warn_on_duplicate_channels(points)
    slope, intercept, r_squared = linear_fit(points)

    fit_points = [point for point in points if point["use_for_fit"]]
    excluded_points = [point for point in points if not point["use_for_fit"]]

    all_channels = np.array([point["channel"] for point in points], dtype=float)
    x_min = all_channels.min() - 300
    x_max = all_channels.max() + 300
    x_line = np.linspace(x_min, x_max, 300)
    y_line = slope * x_line + intercept

    fig, ax = plt.subplots(figsize=(8, 6))

    ax.plot(
        x_line,
        y_line,
        color="tab:blue",
        linewidth=2,
        label=f"Linear fit: E = {slope:.6e} * channel + {intercept:.4f}\n$R^2$ = {r_squared:.6f}",
    )

    ax.scatter(
        [point["channel"] for point in fit_points],
        [point["energy"] for point in fit_points],
        color="tab:blue",
        s=70,
        zorder=3,
        label="Used in fit",
    )

    if excluded_points:
        ax.scatter(
            [point["channel"] for point in excluded_points],
            [point["energy"] for point in excluded_points],
            color="tab:red",
            marker="x",
            s=90,
            linewidths=2,
            zorder=3,
            label="Plotted but excluded from fit",
        )

    for point in points:
        ax.annotate(
            f"{point['label']} ({point['energy']:.3f} MeV)",
            (point["channel"], point["energy"]),
            xytext=(8, 6),
            textcoords="offset points",
            fontsize=9,
        )

    ax.set_title("Gamma-Ray Energy Calibration")
    ax.set_xlabel("Channel")
    ax.set_ylabel("Peak Energy (MeV)")
    ax.grid(True, linestyle="--", alpha=0.4)
    ax.legend()
    fig.tight_layout()
    fig.savefig(output_path, dpi=300)
    plt.show()

    print(f"Calibration equation: E(MeV) = {slope:.8e} * channel + {intercept:.6f}")
    print(f"R^2 = {r_squared:.8f}")
    print(f"Figure saved to: {output_path}")


if __name__ == "__main__":
    output_file = Path("calibration_curve.png")
    make_plot(POINTS, output_file)
```
