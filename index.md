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
      ]
  });">
</script>

# **I. Phần số học**

### 1. Kiểm tra số nguyên tố

*a. Thuật toán cơ bản O(n)*

Cách đơn giản nhất để kiểm tra tính nguyên tố của số tự nhiên là trực tiếp sử dụng định nghĩa số nguyên tố:
> Số tự nhiên $n \geq 2$ là số nguyên tố khi và chỉ khi $n$ không chia hết cho các số tự nhiên $2, 3, ..., n-1$.
