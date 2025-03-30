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

# **I. PHẦN SỐ HỌC**

### **1. Kiểm tra số nguyên tố**

*a. Thuật toán cơ bản $O(n)$*

Cách đơn giản nhất để kiểm tra tính nguyên tố của số tự nhiên là trực tiếp sử dụng định nghĩa số nguyên tố:
> Số tự nhiên $n \geq 2$ là số nguyên tố khi và chỉ khi $n$ không chia hết cho các số tự nhiên $2, 3,\dots, n-1$.

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
*b. Thuật toán tối ưu $O(\sqrt{n})$*

Để tối ưu thuật toán trên, nhận xét rằng nếu $n$ có một ước $d$ sao cho $n-1 \geq d \geq \sqrt{n}$ thì $\dfrac {n}{d}$ cũng là ước của $n$ và có $1 < \dfrac {n}{d} \leq \sqrt{n}$. Suy ra nếu $n$ không chia hết cho các số tự nhiên lớn hơn $1$ và không vượt quá $\sqrt{n}$ thì $n$ cũng không chia hết cho các số tự nhiên lớn hơn $\sqrt{n}$. Từ đó, thay vì xét tính chia hết của $n$ cho $i = 2, 3,\dots, n-1$ ta chỉ cần xét $i = 2, 3,\dots, [\sqrt{n}]$.

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
**Chú ý:** Có thể sử dụng nhiều số nguyên tố đầu tiên để tối ưu thuật toán hơn. Về lý thuyết, nếu $k$ là số số nguyên tố được dùng càng lớn thì vòng lặp chạy càng nhanh. Tuy nhiên, với $k = 50$, độ phức tạp vòng lặp ***for***  là $O(\dfrac {\sqrt{n}}{10})$. Và kể cả với $k = 6 \cdot 10^5$ thì độ phức tạp thuật của vòng lặp ***for***  vẫn là $O(\dfrac {\sqrt{n}}{30})$.

Do đó thuật toán này có thể không đủ nhanh để giải quyết giới hạn $n \leq 10^{18}$, hoặc $n \leq 10^9$ nhưng phải kiểm tra $10^6$ số $n$ trở lên. Để giải quyết các bài toán có giới hạn lớn như thế, ta phải sử dụng đến các phương pháp xác suất.

### **2. Sàng nguyên tố Eratosthenes (Sieve of Eratosthenes)**

Khi cần tìm ra các số nguyên tố từ $1$ đến $n$, ta có thể duyệt từng số và kiểm tra tính nguyên tố của nó. Và ý tưởng đó cho ta một thuật toán $O(\sqrt{n})$.

> Tuy nhiên, một nhà toán học cổ Hy Lạp tên là Eratosthenes đã "phát minh" ra một "thuật toán" hiệu quả hơn. Ban đầu, Eratosthenes đã lấy lá cọ và ghi tất cả các số từ $2$ cho đến $100$. Sau đó, ông đã chọc thủng các hợp số và giữ nguyên các số nguyên tố. Bảng số nguyên tố còn lại trông rất giống một cái sàng. Cho đến ngày nay, "thuật toán" này được phổ biến rộng rãi với cái tên **sàng nguyên tố Eratosthenes.**

- Ban đầu, ta cho tất cả số từ $2$ đến $n$ vào sàng và đánh dấu tất cả các số. (Các số không được đánh dấu sau cùng sẽ bị loại khỏi sàng).
- Duyệt lần lượt các số từ $2$ đến $n$. Nếu số đang xét:
  - Đã được đánh dấu $\Rightarrow$ số nguyên tố: ta bỏ đánh dấu tất cả các bội (khác chính nó) của số nguyên tố này để loại các bội ấy ra khỏi sàng.
  - Không được đánh dấu $\Rightarrow$ hợp số: ta bỏ qua số này.
- Sau khi duyệt xong các số còn lại trong sàng, hay nói cách khác các số được đánh dấu là số nguyên tố.

Cài đặt:
```cpp
const int maxn = 1e6 + 7;
vector <bool> prime(maxn, true);
void sieve(int n)
{
	prime[0] = prime[1] = false;
	for (int i = 2 ; i <= n ; ++i) {
		if (prime[i]) {
			for (int j = i*2 ; j <= n ; j += i)
				prime[j] = false;
		}
	}
}
```
**Độ phức tạp thời gian: $O(n \log(\log n))$**

**Độ phức tạp không gian: $O(n)$**

> **Nhận xét**  
> Xét $X = k \cdot p$ là bội của số nguyên tố $p$.  
> Nếu như $p < X < p^2$, ta có $1 < k < p$. Ta suy ra $k$ phải có một ước nguyên tố nhỏ hơn $p$.  
> Vì thế, $X = k \cdot p$ đã bị sàng loại đi trong các vòng lặp trước đó và ta **chỉ cần xét $X \geq p^2$.**

Dựa vào *nhận xét* trên, ta có cải tiến như sau:
```cpp
const int maxn = 1e6 + 7;
vector <bool> prime(maxn, true);
void sieve(int n)
{
	prime[0] = prime[1] = false;
	for (int i = 2 ; i * i <= n ; ++i) {
		if (prime[i]) {
			for (int j = i*i ; j <= n ; j += i)
				prime[j] = false;
		}
	}
}
```
Dưới đây là hình minh họa cho cải tiến trên. *Nguồn: [Wikipedia](https://vi.wikipedia.org/wiki/S%C3%A0ng_Eratosthenes)*

![Sàng Eratosthenes](https://upload.wikimedia.org/wikipedia/commons/b/b8/Animation_Sieb_des_Eratosthenes_%28vi%29.gif)

# **II. CHẶT NHỊ PHÂN**

# **III. QUY HOẠCH ĐỘNG - *DYNAMIC PROGRAMMING (DP)***

### **1. Dãy con tăng dài nhất - *Longest Increasing Subsequence (LIS)***

*a. Thuật cơ bản $O(n^2)$*

Cài đặt:
```cpp
vector <int> dp(n+1, 1);
for (int i = 1 ; i <= n ; ++i) {
	for (int j = 1 ; j < i ; ++j)
		dp[i] = max(dp[i], dp[i-1] + 1);
}
```

*b. Thuật tối ưu $O(n \log n)$*

Cài đặt:
```cpp
// Code
```

### **2. Vali B - *Knapsack 01 (Balo 01)***

# **IV. ĐỒ THỊ**
