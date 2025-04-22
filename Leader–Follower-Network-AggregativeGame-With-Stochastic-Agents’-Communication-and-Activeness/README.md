To prove that the sum of $ T_2^j $ is less than infinity, let's carefully analyze the structure and properties of $ T_2^j $ as presented in the document. Here's the reasoning:

---

### **Definition of $ T_2^j $:**
From the proof in the document, $ T_2^j $ is defined as:
$$
T_2^j = 2L \sum_{n \in \mathcal{N}} \sum_{m \in \mathcal{N}_n} B_n w_{nm} \sum_{k' \in \mathcal{K}_j'} \alpha_n^{k'} ||\Delta \tilde{x}_{nm}^{k'}||,
$$
where:
- $ \mathcal{K}_j' = \{k_{j-1}^L + 1, \dots, k_j^L\} $,
- $ \Delta \tilde{x}_{nm}^{k'} = \tilde{x}_{nm}^{k'} - x_m^{k'} $,
- $ \alpha_n^{k'} $ are step sizes satisfying Assumption \ref{step_size_assumption},
- $ w_{nm} $ are weights from the communication graph,
- $ B_n $ is a constant such that $ ||x_1 - x_2|| \leq B_n $ for all $ x_1, x_2 \in \mathcal{X}_n $.

---

### **Key Properties to Prove $ \sum_{j=0}^\infty T_2^j < \infty $:**

1. **Convergence of $ \sum_{k=0}^\infty \alpha_n^k ||\Delta \tilde{x}_{nm}^k|| $:**
   From Lemma \ref{convegence_of_the_series}, it is proven that:
   $$
   \sum_{k=0}^\infty \alpha_n^k ||\Delta \tilde{x}_{nm}^k|| < \infty \quad \text{almost surely}.
   $$
   This result ensures that the cumulative weighted differences $ ||\Delta \tilde{x}_{nm}^k|| $ diminish sufficiently fast as $ k \to \infty $.

2. **Finite Sum Over Each Interval $ \mathcal{K}_j' $:**
   Since $ \mathcal{K}_j' $ represents a finite interval of iterations (from $ k_{j-1}^L + 1 $ to $ k_j^L $), the inner summation over $ k' \in \mathcal{K}_j' $ is finite for each $ j $. Specifically:
   $$
   \sum_{k' \in \mathcal{K}_j'} \alpha_n^{k'} ||\Delta \tilde{x}_{nm}^{k'}|| < \infty.
   $$

3. **Boundedness of Constants:**
   - The constants $ L $, $ B_n $, and $ w_{nm} $ are bounded by definition.
   - The step sizes $ \alpha_n^{k'} $ satisfy Assumption \ref{step_size_assumption}, which ensures that $ \sum_{k=0}^\infty (\alpha_n^k)^2 < \infty $ and $ \sum_{k=0}^\infty \alpha_n^k = \infty $.

4. **Summation Over All Intervals $ j $:**
   Combining the above properties, we can write:
   $$
   \sum_{j=0}^\infty T_2^j = 2L \sum_{j=0}^\infty \sum_{n \in \mathcal{N}} \sum_{m \in \mathcal{N}_n} B_n w_{nm} \sum_{k' \in \mathcal{K}_j'} \alpha_n^{k'} ||\Delta \tilde{x}_{nm}^{k'}||.
   $$
   By interchanging the order of summation (justified because all terms are non-negative), this becomes:
   $$
   \sum_{j=0}^\infty T_2^j = 2L \sum_{n \in \mathcal{N}} \sum_{m \in \mathcal{N}_n} B_n w_{nm} \sum_{k'=0}^\infty \alpha_n^{k'} ||\Delta \tilde{x}_{nm}^{k'}||.
   $$

5. **Application of Lemma \ref{convegence_of_the_series}:**
   From Lemma \ref{convegence_of_the_series}, we know that:
   $$
   \sum_{k'=0}^\infty \alpha_n^{k'} ||\Delta \tilde{x}_{nm}^{k'}|| < \infty.
   $$
   Therefore, the entire summation converges, and we conclude:
   $$
   \sum_{j=0}^\infty T_2^j < \infty.
   $$

---

### **Conclusion:**
Using the convergence results from Lemma \ref{convegence_of_the_series} and the boundedness of constants $ L $, $ B_n $, and $ w_{nm} $, we have shown that:
$$
\boxed{\sum_{j=0}^\infty T_2^j < \infty.}
$$
