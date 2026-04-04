# Jordan–Wigner Notes

1. Because \(\hat c_j\) is not naively \(\hat \sigma_j^{-}\), we need the parity string to make sure the anticommutation relationship for fermions holds.

   Say
   \[
   \hat c_j = P_{<j}\,\hat \sigma_j^{-}, 
   \qquad
   P_{<j}=\prod_{\ell<j}(1-2\hat n_\ell)
   \]
   where the string is nonlocal.

2. 
   \[
   \hat n_j=\frac{1+\sigma_j^z}{2}.
   \]

3. 
   \[
   \sigma_j^x\sigma_{j+1}^x
   =(\hat\sigma_j^{+}+\hat\sigma_j^{-})(\hat\sigma_{j+1}^{+}+\hat\sigma_{j+1}^{-})
   \]
   \[
   =\hat\sigma_j^{+}\hat\sigma_{j+1}^{+}
   +\hat\sigma_j^{-}\hat\sigma_{j+1}^{-}
   +\hat\sigma_j^{+}\hat\sigma_{j+1}^{-}
   +\hat\sigma_j^{-}\hat\sigma_{j+1}^{+}.
   \]

   With
   \[
   \hat\sigma_j^{+}=P_{<j}\hat c_j^{\dagger},
   \]
   so that
   \[
   \hat\sigma_j^{+}\hat\sigma_{j+1}^{+}
   =P_{<j}\hat c_j^{\dagger}\,P_{<j+1}\hat c_{j+1}^{\dagger}
   =\hat c_j^{\dagger}(1-2\hat n_j)\hat c_{j+1}^{\dagger}.
   \]

   And
   \[
   P_{<j}=(-1)^{\sum_{\ell<j}\hat n_\ell}
   =\prod_{\ell<j}(1-2\hat n_\ell).
   \]

   Also
   \[
   \hat c_j^{\dagger}\hat n_j
   =\hat c_j^{\dagger}\hat c_j^{\dagger}\hat c_j
   =0,
   \]
   \[
   \hat c_j\hat n_j
   =\hat c_j\hat c_j^{\dagger}\hat c_j
   =\hat c_j(1-\hat c_j^{\dagger}\hat c_j)
   =\hat c_j.
   \]

   So,
   \[
   \sigma_j^x\sigma_{j+1}^x
   =\hat c_j^{\dagger}\hat c_{j+1}^{\dagger}
   -\hat c_j\hat c_{j+1}
   +\hat c_j^{\dagger}\hat c_{j+1}
   -\hat c_j\hat c_{j+1}^{\dagger}.
   \]

   Rearranging,
   \[
   =(\hat c_{j+1}^{\dagger}\hat c_j+\hat c_j^{\dagger}\hat c_{j+1})
   -(\hat c_{j+1}^{\dagger}\hat c_j^{\dagger}+\hat c_j\hat c_{j+1}).
   \]

4. 
   \[
   t=\Delta=J,\qquad \mu=2h.
   \]

5. 
   \[
   \mu=0,\qquad t=\Delta,
   \]
   \[
   \gamma_{A,1}\ \text{and}\ \gamma_{B,L}.
   \]

Also, please introduce the Z_2 symmetry in Kitaev chain for me in next response.
