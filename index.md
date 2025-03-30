---
title: "Tổng hợp kiến thức 📚"
---

<script defer src="https://cdn.jsdelivr.net/npm/katex@0.15.3/dist/katex.min.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.15.3/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.15.3/dist/contrib/auto-render.min.js"
  onload="renderMathInElement(document.body, {
      delimiters: [
          {left: '$$', right: '$$', display: true},
          {left: '$', right: '$', display: false}
      ],
      ignoredTags: ['script', 'noscript', 'style', 'textarea', 'pre']
  });">
</script>

# **I. Phần số học**

### 1. Kiểm tra số nguyên tố

*a. Thuật toán cơ bản O(n)*

Cách đơn giản nhất để kiểm tra tính nguyên tố của số tự nhiên là trực tiếp sử dụng định nghĩa số nguyên tố:
> Số tự nhiên $n \geq 2$ là số nguyên tố khi và chỉ khi $n$ không chia hết cho các số tự nhiên $2, 3, ..., n-1$.

Code:
```cpp
bool prime(int n)
{
    if (n < 2) return false;
    for (int i = 2; i < n; ++i)
        if (n % i == 0)
            return false;
    return true;
}
```
*b. Thuật toán tối ưu O($\sqrt{n}$)*

Để tối ưu thuật toán trên, nhận xét rằng nếu $n$ có một ước $d$ sao cho $n-1 \geq d \geq \sqrt{n}$ thì $\dfrac {n}{d}$ cũng là ước của $n$ và có $1 < \dfrac {n}{d} \leq \sqrt{n}$. Suy ra nếu $n$ không chia hết cho các số tự nhiên lớn hơn $1$ và không vượt quá $\sqrt{n}$ thì $n$ cũng không chia hết cho các số tự nhiên lớn hơn $\sqrt{n}$. Từ đó, thay vì xét tính chia hết của $n$ cho $i = 2, 3,..., n-1$ ta chỉ cần xét $i = 2, 3,...,[\sqrt{n}]$.
