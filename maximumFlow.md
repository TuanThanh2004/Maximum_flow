# Luồng cực đại(Maximum flow)

### Bài toán phát biểu input-output

**Input:**

1. Đồ thị: Đây là một đồ thị có hướng, với các đỉnh và các cạnh. Đồ thị biểu diễn mô hình hệ thống hoặc mạng mà chúng ta đang nghiên cứu. Đồ thị bao gồm các đỉnh đại diện cho các nút hoặc điểm trong hệ thống và các cạnh đại diện cho các kết nối hoặc luồng dữ liệu giữa các đỉnh.
2. Đỉnh nguồn (source): Đây là đỉnh trong đồ thị từ đó bắt đầu các đường luồng. Tại đỉnh nguồn, luồng được bắt đầu và bắt đầu chảy qua các cạnh đến các đỉnh khác.
3. Đỉnh đích (sink): Đây là đỉnh trong đồ thị mà chúng ta muốn đạt được luồng cực đại đến. Đỉnh đích thường là nơi mà luồng cần được tập trung hoặc đến được.
4. Các cạnh và khả năng chảy: Mỗi cạnh trong đồ thị sẽ có một khả năng chảy hoặc khả năng truyền dữ liệu. Điều này đại diện cho giới hạn về lượng dữ liệu có thể truyền qua mỗi cạnh. Các khả năng chảy thường được biểu thị bằng các số nguyên hoặc thực dương.
5. Ràng buộc và hạn chế: Có thể có các ràng buộc và hạn chế đối với luồng cực đại. Ví dụ, có thể có giới hạn về tổng lượng luồng chảy từ nguồn đến đích, hoặc giới hạn về lượng luồng chảy qua một số đỉnh cụ thể.

**Output:**

Output của bài toán luồng cực đại là giá trị cực đại của luồng trong đồ thị đã cho.

### Ví dụ

Giả sử chúng ta có một mạng lưới giao thông với các đường và nút. Chúng ta muốn tìm luồng cực đại trong mạng này để biết lượng xe tối đa có thể đi qua các con đường trong cùng một thời điểm.

Ví dụ, hãy xem xét mạng lưới giao thông sau đây:

```
scssCopy code
      (A)
     /   \
   4/     \6
   /       \
 (B)---5-->(C)
   |\     /|
  3| \   / |4
   |  \ /  |
   |   X   |
  2|  / \  |3
   | /   \ |
 (D)---2-->(E)
     \   /
    5\ /1
     (F)

```

Trong đồ thị trên, các đỉnh được biểu diễn bởi các chữ cái A, B, C, D, E, F và các cạnh được gắn với các giá trị là trọng số (lượng xe tối đa có thể đi qua).

Chúng ta muốn tìm luồng cực đại từ đỉnh A (nguồn) đến đỉnh F (đích). Kết quả của thuật toán luồng cực đại sẽ cho chúng ta biết giá trị luồng cực đại và cách các cạnh trong mạng được sử dụng để chuyển giao lượng dữ liệu này.

Ví dụ, kết quả có thể là:

- Giá trị luồng cực đại là 8.
- Các cạnh được sử dụng để chuyển giao lượng dữ liệu cực đại là (A-C), (C-F) với lưu lượng là 6 và (A-B), (B-D), (D-F) với lưu lượng là 2.

Điều này cho thấy rằng trong mạng lưới giao thông này, ta có thể chuyển tối đa 8 lượng xe từ đỉnh A đến đỉnh F, và việc chuyển lượng xe này được thực hiện thông qua các con đường đã được xác định trong luồng cực đại.

### Ứng dụng

Luồng cực đại (Maximum Flow) là một khái niệm quan trọng trong lý thuyết đồ thị và có nhiều ứng dụng trong thực tế. Dưới đây là một số ví dụ về ứng dụng của luồng cực đại:

1. Mạng giao thông: Luồng cực đại được sử dụng để tối ưu hóa việc lưu lượng giao thông trong mạng lưới giao thông. Ví dụ, nó có thể được sử dụng để tìm cách phân phối xe cộ hiệu quả trên các tuyến đường hoặc định tuyến trong hệ thống giao thông để giảm ùn tắc và tối ưu hóa thời gian di chuyển.
2. Mạng điện: Luồng cực đại được áp dụng trong việc phân phối điện trong mạng lưới điện. Nó giúp xác định các tuyến dẫn điện tối ưu từ các nhà máy điện đến các điểm tiêu thụ, đảm bảo rằng năng lượng được truyền tải một cách hiệu quả và ổn định.
3. Mạng máy tính: Luồng cực đại có thể được sử dụng để tối ưu hóa việc truyền tải dữ liệu trong mạng máy tính. Ví dụ, nó có thể được sử dụng để xác định đường dẫn tối ưu cho việc truyền tải dữ liệu giữa các nút mạng, đảm bảo hiệu suất và băng thông tối đa.
4. Quản lý dòng chảy nước: Luồng cực đại có thể được sử dụng để quản lý và điều tiết dòng chảy nước trong hệ thống cấp nước, hệ thống thoát nước, và các dự án liên quan đến nguồn nước. Nó giúp tối ưu hóa việc cấp nước, kiểm soát mức nước và đảm bảo sự ổn định của hệ thống.
5. Kỹ thuật phần mềm: Luồng cực đại cũng được sử dụng trong kỹ thuật phần mềm để phân phối tài nguyên và quản lý luồng công việc. Ví dụ, nó có thể được áp dụng để phân chia tài nguyên máy tính, lập lịch thực thi công việc, và tối ưu hóa hiệu suất hệ thống.

### Các tính chất của bài toán

Trong thuật toán luồng cực đại, có một số khái niệm quan trọng cần hiểu:

1. Mạng luồng (Flow Network): Là một đồ thị có hướng được gắn với trọng số (thường là lưu lượng) trên các cạnh. Mạng luồng bao gồm một nguồn (source) và một đích (sink).
2. Luồng (Flow): Là lượng thông qua mỗi cạnh trong mạng luồng. Luồng được đánh giá theo trọng số (thường là lưu lượng) và có giới hạn trên từng cạnh.
3. Luồng cực đại (Maximum Flow): Là luồng có giá trị lớn nhất mà có thể chảy từ nguồn đến đích trong mạng luồng.
4. Cắt (Cut): Là một tập hợp các cạnh trong mạng luồng mà khi loại bỏ chúng, không có luồng nào có thể chảy từ nguồn đến đích.
5. Cắt cực tiểu (Minimum Cut): Là cắt có tổng trọng số (tổng lưu lượng) của các cạnh là nhỏ nhất trong tất cả các cắt trong mạng luồng.
6. Đường tăng (Augmenting Path): Là một đường đi từ nguồn đến đích trong mạng luồng mà cung cấp cơ hội để tăng giá trị luồng.
7. Thuật toán Ford-Fulkerson: Là một thuật toán sử dụng việc tìm đường tăng liên tiếp để tăng giá trị luồng cho đến khi không còn đường tăng nào nữa, từ đó tìm được luồng cực đại.
8. Đồ thị còn dư (Residual Graph): Là một đồ thị mới được tạo ra từ mạng luồng ban đầu sau mỗi lần tăng giá trị luồng, để đại diện cho các đường tăng tiềm năng khác.
9. Đường tăng cực đại (Augmenting Path): Đường tăng cực đại là một đường đi từ nguồn đến đích trong mạng luồng, trong đó cung cấp khả năng tăng giá trị luồng hiện tại.
10. .Đồ thị còn dư (Residual Graph): Đồ thị còn dư là một đồ thị tạo ra từ mạng luồng ban đầu sau khi áp dụng thuật toán Ford-Fulkerson. Đồ thị còn dư cho biết khả năng tăng giá trị luồng trên các cung của đồ thị ban đầu.

### Ý tưởng của bài toán

Ý tưởng chính của thuật toán luồng cực đại là tìm cách tăng giá trị luồng từ nguồn đến đích trong mạng đồ thị. Thuật toán tiến hành lặp lại việc tìm đường đi tăng giá trị luồng (gọi là đường tăng cực đại) và tăng giá trị luồng trên các cung của đường đi đó cho đến khi không còn đường đi tăng nào nữa.

Các bước chính của thuật toán luồng cực đại (thường dựa trên thuật toán Ford-Fulkerson) bao gồm:

1. Khởi tạo giá trị luồng ban đầu là 0 trên tất cả các cung của đồ thị.
2. Tìm một đường tăng cực đại từ nguồn đến đích trong đồ thị còn dư sử dụng một thuật toán tìm đường đi như BFS (Breadth-First Search) hoặc DFS (Depth-First Search).
3. Nếu không tìm thấy đường tăng cực đại, thuật toán dừng và kết thúc. Giá trị luồng cực đại là tổng giá trị luồng trên các cung đi qua cắt cực tiểu.
4. Nếu tìm thấy đường tăng cực đại, tăng giá trị luồng trên các cung của đường đi đó bằng giá trị tối thiểu của các cung trên đường đi.
5. Lặp lại bước 2 và bước 4 cho đến khi không còn đường tăng cực đại nào nữa.

Kết quả cuối cùng là giá trị luồng cực đại và phân phối luồng trên các cung của đồ thị.

Ý tưởng chính của thuật toán là tận dụng khả năng tăng giá trị luồng thông qua đường tăng cực đại cho đến khi không còn đường tăng nào. Thuật toán đảm bảo tìm ra luồng cực đại trong mạng đồ thị, giúp giải quyết nhiều bài toán thực tế như vận chuyển hàng hóa, phân bổ tài nguyên, lập lịch và tối ưu hóa mạng.

# Đánh giá

## Độ bất biến của toán

**Độ bất biến của thuật toán luồng cực đại** liên quan đến tính chất mà thuật toán đảm bảo trong quá trình tìm kiếm và tăng giá trị luồng. Một trong những độ bất biến quan trọng của thuật toán luồng cực đại là định lí bất biến luồng (flow conservation).

Định lí bất biến luồng (flow conservation) cho rằng:

- Tại mọi đỉnh trong đồ thị, tổng giá trị luồng đi vào phải bằng tổng giá trị luồng đi ra.
- Ngoại trừ nguồn và đích, tổng giá trị luồng đi vào và luồng đi ra của một đỉnh bằng nhau.

Định lí này đảm bảo tính chất cân bằng luồng trong mạng đồ thị. Nó được duy trì và bảo toàn trong quá trình tăng giá trị luồng trên các cung của đồ thị.

Định lí bất biến luồng là quan trọng trong thuật toán luồng cực đại, vì nó giúp đảm bảo tính hợp lệ của luồng trong mạng và đóng vai trò quan trọng trong việc tìm kiếm và tăng giá trị luồng từ nguồn đến đích.

Tuy nhiên, cần lưu ý rằng độ bất biến của thuật toán luồng cực đại không áp dụng cho các thuật toán cụ thể khác như thuật toán tìm kiếm đường đi tăng cực đại. Điều này chỉ áp dụng cho thuật toán chính của luồng cực đại, chẳng hạn như thuật toán Ford-Fulkerson.

**Để giữ độ bất biến của thuật toán luồng cực đại**, ta cần tuân thủ các quy tắc và tính chất cơ bản của thuật toán. Dưới đây là một số cách để đảm bảo độ bất biến của thuật toán luồng cực đại:

1. Cập nhật luồng: Trong quá trình tìm kiếm luồng cực đại, cần cập nhật giá trị luồng trên các cạnh để đảm bảo luồng tăng dần và không vượt quá giới hạn trên các cạnh.
2. Cập nhật hiệu chỉnh: Khi tìm thấy một đường tăng luồng, cần cập nhật hiệu chỉnh trên các cạnh để đảm bảo luồng cực đại.
3. Kiểm tra tính khả thi của luồng: Sau khi tìm thấy luồng cực đại, cần kiểm tra tính khả thi của luồng để đảm bảo không tồn tại đường tăng luồng nữa.
4. Quy tắc bảo toàn luồng: Trong quá trình cập nhật luồng và hiệu chỉnh, cần tuân thủ quy tắc bảo toàn luồng, tức là tổng luồng vào một đỉnh bằng tổng luồng ra khỏi đỉnh đó.
5. Quy tắc bảo toàn hiệu chỉnh: Trong quá trình cập nhật hiệu chỉnh, cần tuân thủ quy tắc bảo toàn hiệu chỉnh, tức là tổng hiệu chỉnh trên các cạnh trong một đường tăng luồng bằng không.
6. Đánh dấu và gỡ đánh dấu: Để tránh lặp lại các đỉnh và cạnh trong quá trình tìm kiếm luồng, ta có thể đánh dấu các đỉnh và cạnh đã được xem xét và gỡ đánh dấu sau khi hoàn thành tìm kiếm.

## Độ phức tạp của toán

**Thời gian:**

- Tốt nhất (best case): O(Ef), trong đó E là số cung của đồ thị và f là giá trị luồng cực đại. Trường hợp tốt nhất xảy ra khi thuật toán tìm được luồng cực đại sau một số lần tăng giá trị luồng nhỏ.
- Xấu nhất (worst case): O(E^2f), trong đó E là số cung của đồ thị và f là giá trị luồng cực đại. Trường hợp xấu nhất xảy ra khi thuật toán phải thực hiện nhiều lần tăng giá trị luồng để tìm được luồng cực đại.
- Trung bình (average, amortized): Thời gian trung bình của thuật toán luồng cực đại phụ thuộc vào cách triển khai cụ thể và cách đồ thị được xây dựng. Trung bình thường được xấp xỉ bằng O(E^2f), nhưng có thể thay đổi tùy thuộc vào đặc điểm của đồ thị.

# Mã giả

```
#include <iostream>
#include <vector>
#include <queue>
#include <climits>

using namespace std;

// Định nghĩa số lượng đỉnh tối đa trong đồ thị
#define MAX_V 100

// Hàm tìm đường đi từ đỉnh nguồn đến đỉnh đích trong đồ thị sử dụng BFS
bool bfs(int residualGraph[MAX_V][MAX_V], int source, int sink, int parent[]) {
    bool visited[MAX_V] = {false};
    queue<int> q;
    q.push(source);
    visited[source] = true;
    parent[source] = -1;

    while (!q.empty()) {
        int u = q.front();
        q.pop();

        for (int v = 0; v < MAX_V; v++) {
            if (!visited[v] && residualGraph[u][v] > 0) {
                q.push(v);
                parent[v] = u;
                visited[v] = true;
            }
        }
    }

    return visited[sink];
}

// Hàm tính luồng cực đại trong đồ thị sử dụng thuật toán Ford-Fulkerson
int maxFlow(int graph[MAX_V][MAX_V], int source, int sink) {
    int residualGraph[MAX_V][MAX_V];
    for (int u = 0; u < MAX_V; u++) {
        for (int v = 0; v < MAX_V; v++) {
            residualGraph[u][v] = graph[u][v];
        }
    }

    int maxFlow = 0;
    int parent[MAX_V];

    while (bfs(residualGraph, source, sink, parent)) {
        int pathFlow = INT_MAX;
        for (int v = sink; v != source; v = parent[v]) {
            int u = parent[v];
            pathFlow = min(pathFlow, residualGraph[u][v]);
        }

        for (int v = sink; v != source; v = parent[v]) {
            int u = parent[v];
            residualGraph[u][v] -= pathFlow;
            residualGraph[v][u] += pathFlow;
        }

        maxFlow += pathFlow;
    }

    return maxFlow;
}

int main() {
    // Khởi tạo đồ thị và các cạnh
    int graph[MAX_V][MAX_V] = {
        {0, 16, 13, 0, 0, 0},
        {0, 0, 10, 12, 0, 0},
        {0, 4, 0, 0, 14, 0},
        {0, 0, 9, 0, 0, 20},
        {0, 0, 0, 7, 0, 4},
        {0, 0, 0, 0, 0, 0}
    };

    int source = 0;
    int sink = 5;

    int maxFlowValue = maxFlow(graph, source, sink);
    cout << "Giá trị luồng cực đại: " << maxFlowValue << endl;

    return 0;
}
```

# Cải tiến

Cải tiến của thuật toán luồng cực đại đã được đề xuất và nghiên cứu để tăng hiệu suất và giảm độ phức tạp. Dưới đây là một số cải tiến phổ biến của thuật toán luồng cực đại:

1. Thuật toán Edmonds-Karp: Đây là một phiên bản cải tiến của thuật toán Ford-Fulkerson. Trong thuật toán này, sử dụng BFS (Breadth-First Search) để tìm đường tăng luồng với chi phí nhỏ nhất từ nguồn đến đích. Việc sử dụng BFS giúp tìm kiếm đường tăng luồng nhanh hơn và đảm bảo tìm được đường tăng luồng ngắn nhất.
2. Thuật toán Dinic: Đây là một thuật toán cải tiến khác của thuật toán luồng cực đại. Thuật toán Dinic sử dụng khái niệm của các khối mở rộng (blocking flows) để tăng cường luồng. Thuật toán này sử dụng kỹ thuật cắt đôi (bisection) và xây dựng các mạng cấu trúc phụ (level graph) để tìm đường tăng luồng nhanh hơn.
3. Thuật toán Push-Relabel: Đây là một nhóm thuật toán cải tiến dựa trên việc đẩy (push) và tái thiết lập (relabel) các đỉnh trong đồ thị. Các thuật toán như thuật toán Preflow-Push và thuật toán Highest-Label-First (HLF) sử dụng các chiến lược thông minh để tìm đường tăng luồng hiệu quả.
4. Cải tiến trên cấu trúc dữ liệu: Đồng thời với việc cải tiến thuật toán, cải tiến cấu trúc dữ liệu cũng đóng vai trò quan trọng trong tăng hiệu suất của thuật toán luồng cực đại. Sử dụng các cấu trúc dữ liệu như hàng đợi ưu tiên (priority queue), cây heap, cây AVL, v.v. có thể giúp tối ưu hóa việc thao tác và truy vấn trên đồ thị.
5. Kỹ thuật Scaling: Kỹ thuật Scaling được áp dụng để giảm số lần lặp trong thuật toán luồng cực đại bằng cách tìm kiếm các đường tăng luồng theo thứ tự tăng dần của các trọng số. Bằng cách lựa chọn một ngưỡng (scale) phù hợp và chỉ tìm kiếm các đường tăng luồng cóchỉ tìm kiếm các đường tăng luồng có trọng số lớn hơn hoặc bằng ngưỡng đó, thuật toán Scaling giúp giảm đáng kể số lần lặp cần thiết để tìm được luồng cực đại.
6. Thuật toán trong mạng với cấu trúc đặc biệt: Trong một số trường hợp, khi mạng có cấu trúc đặc biệt như mạng hai phân đồ thị, mạng mũi tên, mạng cực đại, v.v., có thể áp dụng thuật toán đặc thù cho từng trường hợp để tối ưu hóa thuật toán luồng cực đại. Ví dụ như thuật toán Hopcroft-Karp cho mạng hai phân đồ thị, thuật toán Dinic cho mạng cực đại, v.v.
7. Paralellization: Trong các bài toán luồng cực đại quy mô lớn, sử dụng kỹ thuật song song (parallelization) có thể tăng tốc đáng kể quá trình tính toán. Bằng cách chia công việc thành nhiều luồng xử lý và thực hiện tính toán song song trên các luồng đó, thuật toán luồng cực đại có thể được thực hiện nhanh chóng và hiệu quả hơn.

# Bài tập

Dưới đây là một số bài tập về luồng cực đại:

1. Bài toán Đường cắt tối thiểu (Minimum Cut): Cho một đồ thị có hướng với các trọng số trên các cạnh và hai đỉnh nguồn và đích. Hãy tìm một đường cắt có tổng trọng số nhỏ nhất, tức là tổng trọng số của các cạnh chạy từ nguồn đến đích bị cắt.
2. Bài toán Đường đi tối đa (Maximum Flow Path): Cho một đồ thị có hướng với các trọng số trên các cạnh và hai đỉnh nguồn và đích. Hãy tìm một đường đi từ nguồn đến đích có tổng trọng số lớn nhất, tức là tổng trọng số của các cạnh trên đường đi đó.
3. Bài toán Ghép cặp tối đa (Maximum Bipartite Matching): Cho một đồ thị hai phân đồ thị có hướng với hai tập đỉnh X và Y và các cạnh chỉ nối giữa các đỉnh trong X và Y. Hãy tìm một ghép cặp có số cạnh tối đa, tức là tìm cách ghép các đỉnh trong X với các đỉnh trong Y sao cho số cạnh được ghép là lớn nhất.
4. Bài toán Flows và Cuts: Cho một đồ thị có hướng với các trọng số trên các cạnh, hãy tìm luồng cực đại từ một đỉnh nguồn đến một đỉnh đích và tìm một đường cắt tối thiểu trong đồ thị đó.
5. Bài toán Multi-Commodity Flow: Cho một đồ thị có hướng với các trọng số trên các cạnh và nhiều cặp đỉnh nguồn và đích. Hãy tìm luồng cực đại từ các đỉnh nguồn đến các đỉnh đích sao cho luồng từ mỗi cặp đỉnh nguồn và đích không vượt quá một giới hạn.