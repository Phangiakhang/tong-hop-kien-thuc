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

Cài đặt:
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

Cài đặt:
```cpp
bool prime(int n)
{
	if (n < 2) return false;
	for (int i = 2; i*i <= n; ++i)
		if (n % i == 0)
			return false;
	return true;
}
```
*c. Thuật toán nâng cao*

Để ý nếu số nguyên tố $n$ lẻ thì $n$ không chia hết cho một số chẵn bất kì. Do đó nếu $n > 2$, ta chỉ cần xét các số $i$ lẻ thuộc đoạn $[2, [\sqrt{n}]]$. Tương tự, nếu $n > 3$ thì ta chỉ cần xét $i$ là các số không chia hết cho $3$. Từ hai nhận xét trên, nếu $n > 3$ thì ta chỉ cần xét các số $i$ sao cho $i$ chia $6$ dư $1$ hoặc $5$.

Cài đặt:
```cpp
bool prime(int n)
{
	if (n == 2 || n == 3)
		return true;
	if (n < 3 || n % 2 == 0 || n % 3 == 0)
		return false;
	for (int i = 5; i * i <= n; i += 6)
		if (n % i == 0 || n % (i + 2) == 0)
			return false;
	return true;
}
```
