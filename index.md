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

# **📌 MỤC LỤC**

- [**I. PHẦN SỐ HỌC**](#i-phần-số-học)
	- [1. Kiểm tra số nguyên tố](#1-kiểm-tra-số-nguyên-tố)
	- [2. Sàng nguyên tố Eratosthenes (Sieve of Eratosthenes)](#2-sàng-nguyên-tố-eratosthenes-sieve-of-eratosthenes)
	- [3. Phân tích thừa số nguyên tố](#3-phân-tích-thừa-số-nguyên-tố)
	- [4. Phi hàm Euler](#4-phi-hàm-euler)
	- [5. Nghịch đảo modulo](#5-nghịch-đảo-modulo)
	- [6. Sàng nguyên tố $10^{12}$](#6-sàng-nguyên-tố-1012)
	- [7. Thuật toán Rabin - Miller kiểm tra số nguyên tố](#7-thuật-toán-rabin---miller-kiểm-tra-số-nguyên-tố)
- [**II. STANDARD TEMPLATE LIBRARY (STL)**](#ii-standard-template-library-stl)
	- [1. ITERATOR](#1-iterator)
- [**III. CẤU TRÚC DỮ LIỆU VÀ GIẢI THUẬT**](#iii-cấu-trúc-dữ-liệu-và-giải-thuật)
	- [1. Cây phân đoạn - Segment tree](#1-cây-phân-đoạn---segment-tree)
	- [2. Cây chỉ số nhị phân - Fenwick tree](#2-cây-chỉ-số-nhị-phân---fenwick-tree)
	- [3. Thuật toán tham lam](#3-thuật-toán-tham-lam)
	- [4. Đệ quy - Vét cạn (Backtracking)](#4-đệ-quy---vét-cạn-backtracking)
	- [5. Tổng tiền tố - Suffix Array](#5-tổng-tiền-tố---suffix-array)
	- [6. Cửa sổ trượt - Sliding Window](#6-cửa-sổ-trượt---sliding-window)
	- [7. Kỹ thuật 2 con trỏ - Two-pointer technique](#7-kỹ-thuật-2-con-trỏ---two-pointer-technique)
- [**IV. CHẶT NHỊ PHÂN**](#iv-chặt-nhị-phân)
- [**V. QUY HOẠCH ĐỘNG - DYNAMIC PROGRAMMING (DP)**](#v-quy-hoạch-động---dynamic-programming-dp)
	- [1. Dãy con tăng dài nhất - Longest Increasing Subsequence (LIS)](#1-dãy-con-tăng-dài-nhất---longest-increasing-subsequence-lis)
	- [2. Vali B - Knapsack 01 (Balo 01)](#2-vali-b---knapsack-01-balo-01)
	- [3. Bài toán biến đổi xâu](#3-bài-toán-biến-đổi-xâu)
	- [4. Vali A - Knapsack](#4-vali-a---knapsack)
	- [5. Nhân ma trận](#5-nhân-ma-trận)
- [**VI. ĐỒ THỊ**](#vi-đồ-thị)
	- [1. Tìm kiếm theo chiều sâu - Depth-First Search (DFS)](#1-tìm-kiếm-theo-chiều-sâu---depth-first-search-dfs)
	- [2. Tìm kiếm theo chiều rộng - Breadth-First Search (BFS)](#2-tìm-kiếm-theo-chiều-rộng---breadth-first-search-bfs)
	- [3. Đếm số thành phần liên thông của đồ thị vô hướng](#3-đếm-số-thành-phần-liên-thông-của-đồ-thị-vô-hướng)
	- [4. Tìm đường đi trên đồ thị không trọng số](#4-tìm-đường-đi-trên-đồ-thị-không-trọng-số)
	- [5. Thuật toán loang (Flood Fill)](#5-thuật-toán-loang-flood-fill)
	- [6. Tìm đường đi ngắn nhất trên đồ thị có trọng số 0 hoặc 1 (01BFS)](#6-tìm-đường-đi-ngắn-nhất-trên-đồ-thị-có-trọng-số-0-hoặc-1-01bfs)
	- [7. Tìm đường đi ngắn nhất trên ma trận](#7-tìm-đường-đi-ngắn-nhất-trên-ma-trận)
	- [8. Sắp xếp Topo - Thuật toán Kahn](#8-sắp-xếp-topo---thuật-toán-kahn)
	- [9. Kiểm tra chu trình của đồ thị](#9-kiểm-tra-chu-trình-của-đồ-thị)
	- [10. Thuật toán Kosaraju - Đếm số thành phần liên thông mạnh trên đồ thị có hướng](#10-thuật-toán-kosaraju---đếm-số-thành-phần-liên-thông-mạnh-trên-đồ-thị-có-hướng)
	- [11. Disjoint Set Union - DSU](#11-disjoint-set-union---dsu)
	- [12. Thuật toán Kruskal tìm cây khung nhỏ nhất (Minimum Spanning Tree)](#12-thuật-toán-kruskal-tìm-cây-khung-nhỏ-nhất-minimum-spanning-tree)
	- [13. Thuật toán Prim tìm cây khung nhỏ nhất (Minimum Spanning Tree)](#13-thuật-toán-prim-tìm-cây-khung-nhỏ-nhất-minimum-spanning-tree)
	- [14. Thuật toán Tarjan - Bài toán đỉnh trụ (khớp) và cạnh (cầu)](#14-thuật-toán-tarjan---bài-toán-đỉnh-trụ-khớp-và-cạnh-cầu)
	- [15. Thuật toán Dijkstra - Tìm đường đi ngắn nhất trên đồ thị có trọng số không âm](#15-thuật-toán-dijkstra---tìm-đường-đi-ngắn-nhất-trên-đồ-thị-có-trọng-số-không-âm)
	- [16. Chu trình Euler và đường đi Euler](#16-chu-trình-euler-và-đường-đi-euler)
	- [17. Chu trình Hamilton](#17-chu-trình-hamilton)


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

> Tuy nhiên, một nhà toán học cổ Hy Lạp tên là Eratosthenes đã "phát minh" ra một "thuật toán" hiệu quả hơn. Ban đầu, Eratosthenes đã lấy lá cọ và ghi tất cả các số từ 2 cho đến 100. Sau đó, ông đã chọc thủng các hợp số và giữ nguyên các số nguyên tố. Bảng số nguyên tố còn lại trông rất giống một cái sàng. Cho đến ngày nay, "thuật toán" này được phổ biến rộng rãi với cái tên **sàng nguyên tố Eratosthenes.**

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

### **3. Phân tích thừa số nguyên tố**

### **4. Phi hàm Euler**

### **5. Nghịch đảo modulo**

### **6. Sàng nguyên tố $10^{12}$**

### **7. Thuật toán Rabin - Miller kiểm tra số nguyên tố**

# **II. STANDARD TEMPLATE LIBRARY (STL)**

Thư viện STL gồm 4 phần chính:
- Iterators: con trỏ lặp
- Containers: các cấu trúc dữ liệu lưu trữ
- Algorithms: các thuật toán
- Functions: các hàm
  
## **1. ITERATOR**

Iterator (Con trỏ lặp) là một con tror dùng để trỏ tới các phần tử của các Container (CTDL lưu trữ) trong thư viện STL. Mỗi container có một iterator của nó.

Iterator thường dùng để duyệt (lặp) qua các phần tử của container bằng cách sử dụng phép so sánh và các phép toán trên con trỏ với iterator.

Vì Iterator là con trỏ nên có thể sử dụng các phép toán và thao tác tương tự như một con trỏ.

- Phép so sánh: bằng (==) hoặc khác (!=)  
- Phép gán: =  
- Phép toán: cộng (+) hoặc trừ (-) với các số nguyên  
- Phép lấy giá trị: *

Khai báo Iterator:
```cpp
// Khai báo 
<Kiểu_container>::iterator it;
// Trỏ đến phần tử đầu tiên của container
it = <tên_container>.begin();
// Trỏ đến vị trí kết thúc của container (vị trí ngay sau phần tử cuối cùng)
it = <tên_container>.end();
// Duyệt qua container
for (it = <tên_container>.begin() ; it != <tên_container>.end() ; ++it) {
	// Code
}
```
Tất cả các hàm iterator này đều có độ phức tạp là $O(1)$.
> Các đối tượng của thư viện STL thuộc các lớp (Class) trong **namespace std**. Do đó, để thuận tiện khi lập trình, chúng ta nên thêm dòng **using namespace std;** vào đầu chương trình

## **2. CONTAINER**

Một container là một đối tượng cụ thể lưu trữ một tập hợp các đối tượng khác (các phần tử của nó). Nó được thực hiện như các lớp mẫu (class templates).

Container quản lý không gian lưu trữ cho các phần tử của nó và cung cấp một hàm thành viên (member function) để truy cập tới chúng, hoặc trực tiếp thông qua các biến lặp (iterator).

Container có các cấu trúc thường sử dụng trong lập trình như: mảng động - dynamic arrays (vector), hàng đợi - queues (queue), hàng đợi ưu tiên - heaps (priority queue), danh sách liên kết - linked list (list), cây - tree (set), mảng ánh xạ - associative arrays (map), $\dots$

Nhiều container chưa một số hàm thành viên giống nhau. Quyết định sử dụng container nào cho nhu cầu cụ thể nói chung không chỉ phụ thuộc vào các hàm được cung cấp mà còn dựa vào độ hiệu quả của các hàm thành viên của nó (độ phức tạp của các hàm). Điều này đặc biệt đúng với container dãy (sequence containers), mà trong đó có sự khác nhau về độ phức tạp đối với các thao tác chèn/xóa phần tử hay truy cập phần tử.

Sau đây là các container thường dùng nhất.

### **2.1 Vector (Mảng động)**

### **2.2 List (Danh sách liên kết)**

### **2.3 Stack (Ngăn xếp)**

### **2.4 Queue (Hàng đợi)**

### **2.5 Priority queue (Hàng đợi ưu tiên)**

### **2.6 Set (Tập hợp)**

### **2.7 Multiset (Tập hợp trùng lặp)**

### **2.8 Map (Ánh xạ)**

## **3. ALGORITHMS (THUẬT TOÁN)**

# **III. CẤU TRÚC DỮ LIỆU VÀ GIẢI THUẬT**

### **1. Cây phân đoạn - Segment tree**

### **2. Cây chỉ số nhị phân - Fenwick tree**

### **3. Thuật toán tham lam**

### **4. Đệ quy - Vét cạn (Backtracking)**

### **5. Tổng tiền tố - Suffix Array**

*a. Tổng tiền tố mảng 1 chiều - 1D Suffix Array*

Cài đặt tiền xử lí:
```cpp
vector <int> p(n+1);
for (int i = 1 ; i <= n ; ++i)
	p[i] = p[i-1]+a[i];
```

Một số ứng dụng:

Tính nhanh tổng đoạn $[a_{i}, a_{i+1},\dots,a_{j}]$: $\boxed{p[j] - p[i-1]}$

*b. Tổng tiền tố mảng 2 chiều - 2D Suffix Array*

### **6. Cửa sổ trượt - Sliding Window**

### **7. Kỹ thuật 2 con trỏ - Two-pointer technique**

# **IV. CHẶT NHỊ PHÂN**

### **1. Một số hàm liên quan**

### **2. Chặt nhị phân trên miền thực**

# **V. QUY HOẠCH ĐỘNG - DYNAMIC PROGRAMMING (DP)**

### **1. Dãy con tăng dài nhất - Longest Increasing Subsequence (LIS)**

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

### **2. Vali B - Knapsack 01 (Balo 01)**

*a. Tìm giá trị lớn nhất*

Cài đặt: 
```cpp
vector <vector<int>> dp(n+1, vector<int>(S+1, 0))
for (int i = 1 ; i <= n ; ++i) {
	for (int j = 1 ; j <= S ; ++j) {
		dp[i][j] = dp[i-1][j];
		if (j >= w[i])
			dp[i][j] = max(dp[i][j], dp[i-1][j-w[i]] + v[i]);
		}
}
cout << dp[n][S] << "\n";
```

*b. Truy vết*

Cài đặt:
```cpp
set <int> s;
while (n>0)
{
		if (dp[n][S]-dp[n-1][S] != 0) {
				s.insert(n);
				S -= w[n];
		}
		n--;    
}
for (auto x:s) cout << w[x] << " " << v[x] << "\n";
```

### **3. Bài toán biến đổi xâu**

### **4. Vali A - Knapsack**

### **5. Nhân ma trận**

# **VI. ĐỒ THỊ**

### **1. Tìm kiếm theo chiều sâu - Depth-First Search (DFS)**

Cài đặt:
```cpp
vector <bool> vis(maxn, false);
void dfs(int u)
{
	cout << u << " ";
	vis[u] = true;
	for (auto v : adj[u]) {
		if (!vis[v]) 
			dfs(v);
	}
}
```
### **2. Tìm kiếm theo chiều rộng - Breadth-First Search (BFS)**

Cài đặt:
```cpp
vector <bool> vis(maxn, false);
void bfs(int s)
{
	queue <int> q;
	q.push(s);
	vis[s] = true;

	while (!q.empty()) {
		int u = q.front();
		q.pop()

		for (auto v : adj[u]) {
			if (!vis[v]) {
				q.push(v);
				vis[v];
			}
		}
	}
}
```
### **3. Đếm số thành phần liên thông của đồ thị vô hướng**

Cài đặt:
```cpp
int cnt = 0;
for (int i = 1 ; i <= n ; ++i) {
	if (!vis[i]) {
		bfs(i); // hoặc dfs(i)
		++cnt;
	}
}
cout << cnt << "\n";
```

### **4. Tìm đường đi trên đồ thị không trọng số**

*a. Tìm đường đi ngắn nhất - BFS*

Cài đặt:
```cpp
// Code
```

*b. Tìm đường đi dài nhất - DFS*

Cài đặt:
```cpp
// Code
```

### **5. Thuật toán loang (Flood Fill)**

*a. Cài đặt DFS*

Cài đặt:
```cpp

```

*b. Cài đặt BFS*

Cài đặt:
```cpp
// Code
```

### **6. Tìm đường đi ngắn nhất trên đồ thị có trọng số 0 hoặc 1 (01BFS)**

Cài đặt:
```cpp
// Code
```

### **7. Tìm đường đi ngắn nhất trên ma trận**

*a. Cài đặt DFS*

Cài đặt:
```cpp
// Code
```

*b Cài đặt BFS*

Cài đặt:
```cpp
// Code
```

### **8. Sắp xếp Topo - Thuật toán Kahn**

*a. Sắp xếp topo dựa trên DFS*

Cài đặt:
```cpp
// Code
```

*b. Thuật toán Kahn - Xóa dần đỉnh*

Cài đặt:
```cpp
// Code
```

### **9. Kiểm tra chu trình của đồ thị**

*a. Đồ thị vô hướng*

Cài đặt:
```cpp
// Code
```

*b. Đồ thị có hướng*

Cài đặt:
```cpp
// Code
```

### **10. Thuật toán Kosaraju - Đếm số thành phần liên thông mạnh trên đồ thị có hướng**

Cài đặt:
```cpp
// Code
```

### **11. Disjoint Set Union - DSU**

### **12. Thuật toán Kruskal tìm cây khung nhỏ nhất (Minimum Spanning Tree)**

Cài đặt:
```cpp
// Code
```

### **13. Thuật toán Prim tìm cây khung nhỏ nhất (Minimum Spanning Tree)**

Cài đặt:
```cpp
// Code
```

### **14. Thuật toán Tarjan - Bài toán đỉnh trụ (khớp) và cạnh (cầu)**

Cài đặt:
```cpp
// Code
```

### **15. Thuật toán Dijkstra - Tìm đường đi ngắn nhất trên đồ thị có trọng số không âm**

Cài đặt:
```cpp
const int INF = numeric_limits<int>::max();
vector <int> dp(maxn, INF);
void dijkstra(int s)
{
    dp[s] = 0;
    priority_queue <ii, vii, greater<ii>> pq;
    pq.push({0, s});

    while (!pq.empty()) {
        ii top = pq.top();
        int u = top.se;
        ll len = top.fi;

        if (len > dp[u]) continue;
        for (auto it : adj[u]) {
            int v = it.fi;
            ll w = it.se;

            if (dp[v] > dp[u] + w) {
                dp[v] = dp[u] + w;
                pq.push({dp[v], v});
            }
        }
    }
}
```

### **16. Chu trình Euler và đường đi Euler**

*a. Chu trình Euler*

Cài đặt:
```cpp
// Code
```

*b. Đường đi Euler*

Cài đặt:
```cpp
// Code
```

### **17. Chu trình Hamilton**

Cài đặt:
```cpp
// Code
```
