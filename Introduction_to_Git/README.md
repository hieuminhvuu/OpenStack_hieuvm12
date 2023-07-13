# Tìm hiểu kiến thức về Git

---

# **Table of Contents:**

## [I. Chung](#gitI)

-   ### [1. Git là gì ?](#gitI.1)
-   ### [2. Git làm được gì](#gitI.2)
-   ### [3. Các khái niệm cơ bản](#gitI.3)
-   ### [4. Git & Github & Gitlab giống/khác gì nhau ?](#gitI.4)
-   ### [5. Các trạng thái có thể có trong git repository: Untracked, Modified, Umodified, Staged](#gitI.5)

## [II. Config cho git với git config](#gitII)

-   ### [1. Config thông tin cá nhân](#gitII.1)
-   ### [2. Config default/prefered editor](#gitII.2)
-   ### [3. Config global .gitignore](#gitII.3)

## [III. Các thao tác ban đầu](#gitIII)

-   ### [Khởi tạo repo với git init và Clone repo với git repo](#gitIII.1)

## [IV. Git commit](#gitIV)

-   ### [1. Commit trong git là gì](#gitIV.1)
-   ### [2. Một commit chứa những thông tin gì](#gitIV.2)
-   ### [3. Amending](#gitIV.3)

## [V. Làm việc với branch](#gitV)

-   ### [1. Tạo mới branch](#gitV.1)
-   ### [2. Nhảy sang branch khác](#gitV.2)
-   ### [3. Đổi tên branch](#gitV.3)
-   ### [4. Thực hành về git branch](#gitV.4)
-   ### [5. Git checkout đến commit id](#gitV.5)

## [VI. Các thao tác liên quan khác](#gitVI)

-   ### [1. Git Merge](#gitVI.1)
-   ### [2. Git Rebase](#gitVI.2)
-   ### [3. Git Rebase interactive](#gitVI.3)
-   ### [4. Git Rebase khi remote có cập nhật mới](#gitVI.4)
-   ### [5. Git Cherry-pick](#gitVI.5)
-   ### [6. Pull và Push](#gitVI.6)
-   ### [7. Tuỳ chọn force trong git](#gitVI.7)

## [VII. Các thao tác với git remote](#gitVII)

## [VIII. Các thao tác với Stash](#gitVIII)

-   ### [1. Tổng quan về git stash](#gitVIII.1)
-   ### [2. git stash list](#gitVIII.2)
-   ### [3. git stash clear](#gitVIII.3)
-   ### [4. git stash --help](#gitVIII.4)

---

<a name="gitI"></a>

# I. Chung

<a name="gitI.1"></a>

## 1. Git là gì ?

-   Git là hệ thống kiểm soát phiên bản phân tán mà nguồn mở ( Open Source Distributed Version Control System). Các dự án thực tế thường có nhiều nhà phát triển làm việc song song. Vì vậy, một hệ thống kiểm soát phiên bản như Git là cần thiết để đảm bảo không có xung đột mã giữa các nhà phát triển. Ngoài ra, các yêu cầu trong dự án thay đổi thường xuyên. Vì vậy, cần một hệ thống cho phép nhà phát triển quay lại phiên bản cũ hơn của mã.

<a name="gitI.2"></a>

## 2. Git làm được gì

-   Git là một hệ thống quản lý phiên bản phần mềm (version control system) và là một trong những công cụ quản lý phiên bản phổ biến nhất hiện nay. Git là một công cụ giúp cho quá trình phát triển phần mềm trở nên dễ dàng, an toàn và linh hoạt hơn. Nó cung cấp các tính năng và chức năng quản lý phiên bản phần mềm mạnh mẽ và được sử dụng rộng rãi trong cộng đồng phát triển phần mềm. Git có các tính năng và chức năng sau đây:

    -   Quản lý phiên bản mã nguồn: Git cho phép các nhà phát triển lưu trữ và quản lý tất cả các phiên bản của mã nguồn trong một kho lưu trữ (repository). Khi có thay đổi được thực hiện trên mã nguồn, Git sẽ lưu lại các thay đổi đó và cho phép các nhà phát triển xem lại và phục hồi các phiên bản trước đó của mã nguồn.

    -   Hỗ trợ quản lý các nhánh: Git cho phép các nhà phát triển làm việc trên các nhánh riêng biệt của mã nguồn mà không ảnh hưởng đến nhau. Điều này giúp cho quá trình phát triển phần mềm trở nên linh hoạt hơn và giảm thiểu rủi ro khi thay đổi mã nguồn.

    -   Hỗ trợ hợp nhất mã nguồn (merge): Git cho phép các nhà phát triển hợp nhất các thay đổi từ các nhánh khác nhau vào mã nguồn chính một cách dễ dàng và an toàn.

    -   Hỗ trợ các dịch vụ lưu trữ mã nguồn trực tuyến (Github, GitLab, Bitbucket,...): Git được tích hợp với các dịch vụ lưu trữ mã nguồn trực tuyến phổ biến như Github, GitLab, Bitbucket,.. để cho phép các nhà phát triển lưu trữ, chia sẻ và quản lý mã nguồn của mình trong một môi trường trực tuyến và cộng đồng phát triển mở rộng.

    -   Linh hoạt và tiện lợi: Git là một công cụ linh hoạt và tiện lợi, cho phép các nhà phát triển làm việc trên các máy tính khác nhau, trên các nền tảng khác nhau và trong các môi trường khác nhau.

<a name="gitI.3"></a>

## 3. Các khái niệm cơ bản

### Repository

-   Repository hay còn gọi là Repo, dịch ra tiếng Việt có nghĩa là kho, đây chính là nơi chứa tất cả mã nguồn cho một dự án được tạo bởi Git. Có thể hiểu một cách khác là Repository chính khai báo thư mục chứa dự án trên local hoặc remote. Một repo sẽ có hai cấu trúc dữ liệu chính đó là Object store và Index được lưu trữ ẩn trong thư mục .git .

-   Có hai loại repository là local repository và remote repository:

    -   **Local repository**: là repo được cài đặt trên máy tính của lập trình viên, repo này sẽ đồng bộ hóa với remote bằng các lệnh của Git.

    -   **Remote repository**: là repo được cài đặt trên server chuyên dụng, điển hình hiện nay là Github.

### Object store

-   Trong Git, object store là một phần của hệ thống quản lý phiên bản phần mềm (version control system) Git, nơi lưu trữ toàn bộ các đối tượng (objects) của mã nguồn của một dự án. Các đối tượng này bao gồm các thông tin về lịch sử thay đổi của mã nguồn, các phiên bản trước đó của mã nguồn, các thay đổi và nhiều loại đối tượng khác.

-   Object store trong Git là một cơ sở dữ liệu phân tán, có khả năng lưu trữ toàn bộ lịch sử thay đổi của mã nguồn dưới dạng các đối tượng. Các đối tượng này bao gồm:

    -   Blob objects: Lưu trữ nội dung của các tệp trong kho lưu trữ của Git.

    -   Tree objects: Lưu trữ thông tin về cấu trúc thư mục và tệp trong kho lưu trữ của Git.

    -   Commit objects: Lưu trữ thông tin về một lần commit, bao gồm thông tin về tác giả, thời gian thực hiện commit và thông tin về phiên bản mã nguồn.

    -   Tag objects: Lưu trữ thông tin về một phiên bản được gán một nhãn (tag) trong kho lưu trữ của Git.

-   Object store của Git được lưu trữ trên đĩa cứng và được quản lý bởi Git để đảm bảo tính toàn vẹn và độ tin cậy của dữ liệu. Khi một đối tượng được thêm vào kho lưu trữ của Git, Git sẽ sinh ra một mã băm (hash) duy nhất để đại diện cho đối tượng đó. Mã băm này được sử dụng để xác định và truy cập đối tượng trong kho lưu trữ của Git.

-   Object store là một phần quan trọng của Git, giúp cho quá trình quản lý phiên bản phần mềm trở nên dễ dàng và linh hoạt hơn. Nó cho phép các nhà phát triển lưu trữ toàn bộ lịch sử thay đổi của mã nguồn trong một kho lưu trữ duy nhất, giúp cho việc quản lý và theo dõi các thay đổi của mã nguồn trở nên dễ dàng hơn.

-   Đọc thêm : [Git objects](https://viblo.asia/p/git-objects-1Je5EQ9y5nL)

### Index

-   Chỉ mục(index) Git là một vùng dàng dựng giữa thư mục làm việc và kho lưu trữ. Nó được sử dụng để thiết lập một tập hợp các thay đổi mà muốn thực hiện cùng nhau.

-   Có ba vị trí trong Git nơi các thay đổi file có thể cư trú và đây là thư mục làm việc, khu vực dàn dựng và kho lưu trữ. Để hiểu rõ hơn về chỉ mục(index) Git trước hết chúng ta hãy xem sơ qua những nơi này.

<img src= images/git_index.png>

-   Khi thực hiện một lệnh git add, Git sẽ thêm các tệp tin và thư mục được chỉ định vào index. Các thay đổi trên các tệp tin và thư mục này sẽ được Git ghi nhận và chuẩn bị cho một commit sau này. Sau đó, có thể kiểm tra các thay đổi bằng cách sử dụng lệnh git status. Nếu các thay đổi đã được kiểm tra và được xác nhận là hợp lệ, có thể thực hiện một commit để lưu trữ các thay đổi đó trong repository.

-   Index là một phần quan trọng của Git, giúp kiểm soát và quản lý các thay đổi trong repository. Nó cho phép lựa chọn chính xác những thay đổi nào sẽ được commit và khi nào các thay đổi đó sẽ được lưu trữ trong repository. Nó cũng giúp quản lý các phiên bản khác nhau của tệp tin và thư mục trong repository.

-   Đọc thêm : [Tìm hiểu về index trong git](https://cafedev.vn/tu-hoc-git-tim-hieu-ve-indexchi-so-chi-muc-vung-dan-dung-trong-git/)

### Branch

-   Trong Git, branch (nhánh) được sử dụng để phát triển các tính năng mới hoặc sửa lỗi trên một phiên bản hiện tại của mã nguồn mà không ảnh hưởng đến phiên bản đang hoạt động. Branch cho phép các nhà phát triển làm việc độc lập trên các tính năng hoặc các sửa lỗi khác nhau mà không làm ảnh hưởng đến các nhà phát triển khác.

<img src= images/git_branch.png>

-   Mỗi branch trong Git đại diện cho một chuỗi lịch sử thay đổi của mã nguồn. Khi tạo một branch mới, Git sẽ tạo ra một bản sao của toàn bộ lịch sử thay đổi của branch hiện tại. Sau đó, có thể thực hiện các thay đổi trên branch mới mà không ảnh hưởng đến branch hiện tại.

-   Khi hoàn thành các thay đổi trên branch mới, có thể hợp nhất (merge) branch mới này vào branch hiện tại để tích hợp các thay đổi mới vào phiên bản đang hoạt động. Khi hợp nhất branch mới vào branch hiện tại, Git sẽ sử dụng thuật toán hợp nhất để tự động tích hợp các thay đổi mới và giải quyết các xung đột nếu có.

-   Tính năng branch của Git cung cấp nhiều lợi ích cho việc phát triển phần mềm, bao gồm:

    -   Linh hoạt: Branch cho phép các nhà phát triển làm việc độc lập trên các tính năng hoặc sửa lỗi khác nhau mà không ảnh hưởng đến nhau.

    -   An toàn: Branch giúp giảm thiểu rủi ro khi thực hiện các thay đổi trên mã nguồn, vì các thay đổi được thực hiện trên branch mới mà không ảnh hưởng đến branch hiện tại.

    -   Dễ dàng quản lý: Branch giúp các nhà phát triển quản lý và theo dõi các thay đổi trên mã nguồn một cách dễ dàng và hiệu quả.

    -   Tích hợp dễ dàng: Branch cho phép các nhà phát triển hợp nhất các thay đổi từ các nhánh khác nhau vào branch chính một cách dễ dàng và an toàn.

-   Tóm lại, branch là một tính năng mạnh mẽ của Git, giúp các nhà phát triển phát triển phần mềm một cách linh hoạt và an toàn hơn. Nó cho phép các nhà phát triển làm việc độc lập trên các tính năng hoặc sửa lỗi khác nhau mà không làm ảnh hưởng đến nhau và giúp quản lý và theo dõi các thay đổi trên mã nguồn một cách dễ dàng và hiệu quả.

-   Đọc thêm : [Git branch](https://bkhost.vn/blog/git-branches/)

### Git work-flow

-   Git Workflow (quy trình làm việc với Git) là một tập hợp các quy tắc và hướng dẫn để phát triển phần mềm với Git. Git Workflow bao gồm các bước cơ bản để phát triển, kiểm tra và triển khai phần mềm. Dưới đây là một số quy trình làm việc phổ biến với Git:

    -   1. Centralized Workflow: Đây là quy trình làm việc đơn giản nhất và phù hợp với các dự án nhỏ. Một branch master được sử dụng để chứa mã nguồn chính, và các nhánh khác được tạo ra để phát triển các tính năng mới hoặc sửa lỗi. Khi một tính năng hoặc sửa lỗi đã được kiểm tra và hoạt động ổn định, nó được hợp nhất vào branch master để triển khai.

    -   2. Feature Branch Workflow: Đây là quy trình làm việc phổ biến nhất trong Git. Mỗi tính năng hoặc sửa lỗi được phát triển trên một branch riêng biệt (feature branch), và sau đó được hợp nhất vào branch chính (thường là branch develop hoặc master) sau khi đã kiểm tra và hoạt động ổn định.

    -   3. Gitflow Workflow: Đây là một quy trình làm việc phức tạp hơn, phù hợp với các dự án lớn và phức tạp. Nó sử dụng hai branch chính: develop và master. Branch develop chứa các tính năng mới hoặc sửa lỗi được phát triển, trong khi branch master chứa các phiên bản sản phẩm đã được phát hành. Các tính năng mới hoặc sửa lỗi được phát triển trên các branch riêng biệt (feature branch) và sau đó được hợp nhất vào branch develop. Khi một phiên bản mới được phát hành, nó được tạo ra trên branch release và sau đó được hợp nhất vào branch master.

    -   4. Forking Workflow: Đây là quy trình làm việc phù hợp với các dự án mở. Thay vì phát triển trên cùng một repository, mỗi người dùng tạo một bản sao của repository (fork) và phát triển trên đó. Sau đó, họ gửi yêu cầu (pull request) để hợp nhất các tính năng hoặc sửa lỗi vào branch chính của repository gốc.

-   Ví dụ tổng quan về một workflow :
    <img src= images/git_workflow.png>

-   Đọc thêm : [Gitflow workflow](https://viblo.asia/p/co-ban-ve-gitflow-workflow-4dbZNn6yZYM)

### Staging Area

-   Staging Area, hay còn gọi là Index, là một phần của Git được sử dụng để chuẩn bị các thay đổi trước khi commit vào repository. Staging Area cho phép người dùng kiểm soát chính xác những thay đổi nào sẽ được commit vào repository.

-   Khi thực hiện các thay đổi trên các tệp tin và thư mục trong repository của mình, Git sẽ theo dõi các thay đổi này. Tuy nhiên, các thay đổi này chưa được lưu trữ trong repository cho đến khi thực hiện một commit. Trong quá trình này, các thay đổi được lưu trữ trong Staging Area.

-   Để đưa các thay đổi từ Working Directory (thư mục làm việc) vào Staging Area, sử dụng lệnh git add. Lệnh này sẽ thêm các tệp tin và thư mục được chỉ định vào Staging Area. Sau đó, có thể sử dụng lệnh git status để kiểm tra trạng thái của các tệp tin và thư mục trong Staging Area.

-   Khi đã chuẩn bị các thay đổi ở Staging Area, có thể thực hiện một commit để lưu trữ các thay đổi này vào repository. Các thay đổi trong Staging Area sẽ được commit, và các thay đổi này sẽ trở thành một phần của lịch sử thay đổi của repository.

-   Staging Area giúp người dùng có thể kiểm soát chính xác những thay đổi nào sẽ được commit vào repository. Nó cũng cho phép người dùng kiểm tra các thay đổi trước khi commit và giúp người dùng quản lý các phiên bản khác nhau của tệp tin và thư mục trong repository của họ.

    <img src= images/git_staging_area.png>

-   Đọc thêm : [Staging area](https://thachpham.com/tools/hieu-them-ve-commit-va-staging-area-git.html)

<a name="gitI.4"></a>

## 4. Git & Github & Gitlab giống/khác gì nhau ?

### GitLab là gì ?

-   Gitlab là một công cụ quản lý kho lưu trữ được phát triển bơi Gitlab Inc và được sử dụng cho quá trình phát triển phần mềm. Nó cung cấp nhiều loại quản lý mà qua đó chúng tôin có thể hợp lý hoá quy trình làm việc cộng tác của mình để hoàn thành vòng đời phát triển phần mềm.
-   Sau đây là một số tính năng. của GitLab

    -   Nền tảng quản lý kho lưu trữ ấn bản cộng đồng mã nguồn mở
    -   Dễ dàng bảo trì kho lưu trữ trên máy chủ
    -   Cung cấp các công cụ như group milestones, Time Tracking và Issue Tracker, ... để phát triển hiệu quả
    -   Nhiều tính năng xác thực và giao diện người dùng tự phát hơn
    -   quyền người dùng và bảo vệ chi nhánh được tăng cường

### GitHub là gì ?

-   GitHub là một công cụ dịch vụ lưu trữ kho lưu trữ có tính năng cộng tác và kiểm soát truy cập. Nó là một nền tảng để các lập trinh viên sửa lỗi cùng nhau và lưu trữ các dự án nguồn md. GitHub được thiết kế cho các nhà phát triển và để giúp họ theo dỗi các thay đổi của họ trong một dự án thông qua kho lưu trữ.
-   Sau đây là một số tính năng của GitHub:

    -   Chỉ định cột mốc và nhăn cho các dự án.
    -   Chế độ xem so sánh giữa các nhánh được phép
    -   Trang GitHub cho phép chúng tôi xuất bản và lưu trữ các trang web trong GitHub.
    -   Tính năng đánh dấu cú pháp.
    -   Nó cho phép tích hợp API của bên thứ ba để theo dỗi lỗi và lưu trữ đám mây.

-   Giống nhau:

    -   Git, Github và Gitlab đều được sử dụng để quản lý mã nguồn và có thể được sử dụng để phát triển phần mềm.
    -   Cả hai đều sử dụng Git như là nền tảng để quản lý mã nguồn.

-   Khác nhau :
    <img src= images/so_sanh_git.png>

<a name="gitI.5"></a>

## 5. Các trạng thái có thể có trong git repository: Untracked, Modified, Umodified, Staged

-   Các trạng thái có thể có trong git repository: Untracked, Modified, Umodified, Staged

-   Trong Git, các tệp tin và thư mục có thể có các trạng thái khác nhau trong repository. Dưới đây là mô tả các trạng thái phổ biến nhất:

    -   Untracked (Chưa theo dõi): Tệp tin hoặc thư mục mới được tạo ra trong thư mục làm việc (Working Directory) chưa được thêm vào Git. Điều này có nghĩa là Git không theo dõi các thay đổi của tệp tin hoặc thư mục này.

    -   Modified (Đã sửa đổi): Tệp tin đã được thêm vào Git và đã được sửa đổi trong thư mục làm việc. Các thay đổi này chưa được lưu trữ trong Git.

    -   Unmodified (Chưa sửa đổi): Tệp tin đã được thêm vào Git và không có thay đổi nào trong thư mục làm việc.

    -   Staged (Đã chuẩn bị): Tệp tin đã được thêm vào Staging Area và sẵn sàng để được commit vào Git.

      <img src= images/git_staging_state.png>

-   Các trạng thái này được hiển thị bằng lệnh git status. Khi thực hiện các thay đổi trên tệp tin hoặc thư mục, Git sẽ theo dõi các thay đổi này và hiển thị trạng thái của chúng trong git status. Để đưa các thay đổi từ trạng thái Untracked hoặc Modified vào Staging Area, sử dụng lệnh git add. Sau đó, có thể sử dụng lệnh git commit để lưu trữ các thay đổi trong Git.

<a name="gitII"></a>

# II. Config cho git với git config

<a name="gitII.1"></a>

## 1. Config thông tin cá nhân

-   Trong Git, có thể cấu hình thông tin cá nhân của mình bằng cách sử dụng lệnh git config. Các thông tin này bao gồm tên người dùng, địa chỉ email và chữ ký GPG (nếu được sử dụng). Thông tin này sẽ được sử dụng trong các thông điệp commit.

-   Để cấu hình tên người dùng và địa chỉ email, có thể sử dụng lệnh git config như sau:

```
git config --global user.name "Tên "
git config --global user.email "Địa chỉ email"
```

-   Trong đó, --global được sử dụng để cấu hình thông tin này toàn cục trên máy tính. Nếu muốn cấu hình thông tin này cho một repository cụ thể, hãy bỏ --global.

-   Có thể kiểm tra các tùy chọn đã cấu hình bằng lệnh:

```
git config --list
```

Thực hành :

-   Tạo thư mục, init file git
    <img src= images/th1.png>
-   Config với lệnh git config
    <img src= images/th2.png>

<a name="gitII.2"></a>

## 2. Config default/prefered editor

-   Trong Git, có thể thiết lập trình soạn thảo mặc định để sử dụng khi cần phải nhập thông điệp commit hoặc thực hiện một số thao tác khác trong Git. Để cấu hình trình soạn thảo mặc định, có thể sử dụng lệnh git config.

-   Để thiết lập trình soạn thảo mặc định, có thể sử dụng lệnh sau:

```
git config --global core.editor "tên trình soạn thảo"
```

-   Trong đó, "tên trình soạn thảo" là tên của trình soạn thảo mà muốn sử dụng. Ví dụ, nếu muốn sử dụng trình soạn thảo nano, có thể sử dụng lệnh sau:

```
git config --global core.editor "nano"
```

-   Nếu không cấu hình trình soạn thảo mặc định, Git sẽ sử dụng trình soạn thảo mặc định của hệ thống.

-   Sau khi đã cấu hình trình soạn thảo mặc định, có thể sử dụng lệnh git commit để tạo một thông điệp commit mới. Khi thực hiện lệnh này, Git sẽ mở trình soạn thảo mặc định để cho phép nhập nội dung của thông điệp commit. Sau khi nhập xong, lưu và đóng trình soạn thảo, Git sẽ lưu thông điệp commit vào repository.

Thực hành:

-   Tạo thêm 1 file, dùng git add đưa vào trọng thái staging để chuẩn bị commit
    <img src= images/th3.png>
-   Chạy command git commit :
    <img src= images/th4.png>

<a name="gitII.3"></a>

## 3. Config global .gitignore

-   Trong Git, có thể sử dụng tệp .gitignore để chỉ định các tệp tin hoặc thư mục mà Git sẽ bỏ qua khi thực hiện các thao tác như commit, pull và push. Tệp .gitignore có thể được tạo trong thư mục gốc của repository hoặc trong bất kỳ thư mục con nào.

-   Nếu muốn cấu hình một tệp .gitignore toàn cục, có thể sử dụng lệnh git config với tùy chọn core.excludesfile. Để làm điều này, hãy làm theo các bước sau:

-   1. Tạo một tệp .gitignore ở bất kỳ vị trí nào trên hệ thống và thêm các tệp tin và thư mục mà muốn bỏ qua vào tệp này.

Ví dụ, nếu muốn bỏ qua tất cả các tệp tin 1.txt và thư mục node_modules, có thể tạo tệp .gitignore với nội dung sau:

    ```
    1.txt
    node_modules/
    ```

-   2.  Sử dụng lệnh git config để thiết lập đường dẫn đến tệp .gitignore toàn cục:

    ```
    git config --global core.excludesfile /path/to/.gitignore
    ```

Trong đó, /path/to/.gitignore là đường dẫn đến tệp .gitignore toàn cục.

Sau khi đã thiết lập tệp .gitignore toàn cục, Git sẽ bỏ qua các tệp tin và thư mục được liệt kê trong tệp này khi thực hiện các thao tác như commit, pull và push.

<a name="gitIII"></a>

# III. Các thao tác ban đầu

<a name="gitIII.1"></a>

## Khởi tạo repo với git init và Clone repo với git repo

-   Để khởi tạo một repository mới với Git, có thể sử dụng lệnh git init. Đây là cách có thể làm:

        - Mở terminal hoặc command prompt và di chuyển đến thư mục mà muốn tạo repository.
        - Gõ lệnh git init và nhấn Enter. Git sẽ tạo ra một thư mục ẩn có tên .git trong thư mục hiện tại.
        - Thêm các tệp tin vào repository bằng cách sử dụng lệnh git add và tên tệp tin.
        - Tạo một commit với thông điệp mô tả các thay đổi bằng lệnh git commit -m "commit message".
        - Đưa các thay đổi lên repository trên remote server bằng cách sử dụng lệnh git push. Nếu muốn đưa lên repository trên máy chủ cục bộ, có thể sử dụng lệnh git clone để sao chép repository từ remote server.

    Lưu ý rằng khi sử dụng git init, Git sẽ tạo ra một repository trống, và sẽ cần thêm các tệp tin và tạo các commit để theo dõi các thay đổi. Nếu muốn bắt đầu từ một repository đã có sẵn, có thể sao chép repository đó bằng cách sử dụng lệnh git clone.

-   Để sao chép một repository với Git, có thể sử dụng lệnh git clone. Đây là cách có thể làm:

        - Tìm URL của repository muốn sao chép. Nếu đó là một repository trên GitHub, có thể tìm URL bằng cách truy cập vào repository và nhấp vào nút "Clone or download", sau đó sao chép URL được cung cấp.
        - Mở terminal hoặc command prompt và di chuyển đến thư mục muốn sao chép repository đó vào.
        - Gõ lệnh git clone và dán URL repository vào sau lệnh. Ví dụ: git clone https://github.com/user/repo.git.
        - Nhấn Enter để bắt đầu quá trình sao chép. Git sẽ tải về toàn bộ lịch sử và các tệp tin của repository vào thư mục hiện tại.

    Lưu ý rằng khi sao chép một repository bằng git clone, Git sẽ tạo ra một thư mục mới với tên của repository trên remote server, và các tệp tin của repository sẽ được sao chép vào đó. Sau khi sao chép hoàn tất, có thể thực hiện các thao tác trên repository đã sao chép bằng các lệnh Git như bình thường.

Ví dụ : clone repo Viettel-Digital-Talent-2023 về local
<img src= images/th5.png>

<a name="gitIV"></a>

# IV. Git commit

<a name="gitIV.1"></a>

## 1. Commit trong git là gì

-   Trong Git, commit là một hành động để lưu trữ các thay đổi vào repository. Mỗi commit trong Git đại diện cho một phiên bản của repository tại một thời điểm nhất định. Khi thực hiện một commit, Git sẽ lưu trữ một bản sao của tất cả các tệp tin trong repository và các thay đổi được thực hiện trên chúng.

<a name="gitIV.2"></a>

## 2. Một commit chứa những thông tin gì

-   Một commit trong Git bao gồm các phần chính sau đây:

        -   Thông điệp commit: Mô tả các thay đổi đã được thực hiện trong commit đó. Thông điệp này giúp bạn và các thành viên khác trong nhóm hiểu rõ hơn về các thay đổi đã được thực hiện trong commit đó.
        -   Các tệp tin đã thay đổi: Git lưu trữ một bản sao của tất cả các tệp tin đã thay đổi trong commit đó.
        -   Mã hash: Mã hash duy nhất được tạo ra cho mỗi commit, được sử dụng để định danh commit đó trong lịch sử của repository.

Sau khi thực hiện một commit, có thể sử dụng các lệnh Git khác để xem lịch sử commit của repository, so sánh các phiên bản khác nhau của tệp tin và phục hồi các phiên bản trước của repository nếu cần thiết.

<a name="gitIV.3"></a>

## 3. Amending

-   Amending trong Git là hành động sửa đổi commit gần nhất mà bạn đã thực hiện. Nó cho phép thêm hoặc loại bỏ các thay đổi khỏi commit trước đó hoặc chỉnh sửa thông điệp commit. Thao tác này thường được sử dụng khi đã thực hiện một commit nhưng sau đó phát hiện ra rằng đã bỏ sót hoặc thực hiện sai một số thay đổi.

-   Để thực hiện amending trong Git, có thể sử dụng lệnh git commit --amend. Các bước thực hiện như sau:

        - Thực hiện các thay đổi mới hoặc loại bỏ các thay đổi không mong muốn.
        - Sử dụng lệnh git add để thêm các tệp tin đã chỉnh sửa vào staging area.
        - Sử dụng lệnh git commit --amend để thực hiện amending. Nếu muốn chỉnh sửa thông điệp commit, Git sẽ mở một trình soạn thảo văn bản để cho phép chỉnh sửa thông điệp. Nếu không muốn chỉnh sửa thông điệp commit, có thể bỏ qua bước này.
        - Lưu commit mới bằng cách sử dụng lệnh git push --force hoặc git push -f để đẩy commit mới lên remote repository. Lưu ý rằng sử dụng --force có thể ghi đè lịch sử commit trên remote repository, vì vậy hãy sử dụng cẩn thận và chỉ khi chắc chắn rằng không gây ảnh hưởng đến các thành viên khác trong nhóm.

Lưu ý rằng amending chỉ nên được sử dụng trên các commit chưa được đẩy lên remote repository hoặc nếu đã hiểu rõ hậu quả của việc sửa đổi lịch sử commit. Nếu đã đẩy commit lên remote repository, việc amending có thể gây ra xung đột và khó khăn cho các thành viên khác trong nhóm.

<a name="gitV"></a>

# V. Làm việc với branch

<a name="gitV.1"></a>

## 1. Tạo mới branch

-   Trong Git, branch là một phiên bản của repository, được tách ra từ branch chính (thường là branch master). Việc sử dụng branch giúp phát triển tính năng, sửa lỗi hoặc thực hiện các thay đổi khác mà không ảnh hưởng đến phiên bản chính của repository.

-   Để tạo mới một branch trong Git, có thể sử dụng lệnh git branch <tên branch> . Ví dụ, nếu muốn tạo một branch mới có tên là feature-A, có thể sử dụng lệnh sau:

```
git branch feature-A
```

-   Sau khi tạo branch thành công, có thể chuyển sang branch đó bằng cách sử dụng lệnh git checkout <tên branch>. Ví dụ, để chuyển sang branch feature-A, có thể sử dụng lệnh sau:

```
git checkout feature-A
```

-   Nếu muốn tạo mới một branch và chuyển sang branch đó ngay lập tức, có thể sử dụng lệnh git checkout -b <tên branch>. Ví dụ, để tạo một branch mới có tên là feature-B và chuyển sang branch đó, có thể sử dụng lệnh sau:

```
git checkout -b feature-B
```

<a name="gitV.2"></a>

## 2. Nhảy sang branch khác

-   Để chuyển sang một branch khác trong Git, có thể sử dụng lệnh git checkout. Đây là cách thực hiện:

    -   Kiểm tra danh sách các branch hiện có trong repository bằng lệnh git branch.
    -   Chọn branch mà muốn chuyển sang bằng cách sử dụng lệnh git checkout <tên branch>. Ví dụ, để chuyển sang branch có tên là feature-A, có thể sử dụng lệnh git checkout feature-A.
    -   Sau khi chuyển sang branch mới, có thể thực hiện các thao tác trên branch đó, bao gồm thêm, sửa và xóa các tệp tin, thực hiện commit và đẩy các thay đổi lên repository.

-   Lưu ý rằng khi chuyển sang một branch khác, Git sẽ cập nhật các tệp tin trong thư mục làm việc để phù hợp với branch mới đó. Nếu đã thực hiện các thay đổi và commit trên branch hiện tại và chưa đẩy chúng lên remote repository, có thể chuyển sang branch khác mà không mất các thay đổi này. Tuy nhiên, nếu đã đẩy các commit lên remote repository, việc chuyển sang branch khác có thể làm mất các thay đổi chưa được đẩy lên remote repository.

<a name="gitV.3"></a>

## 3. Đổi tên branch

-   Để đổi tên một branch trong Git, có thể sử dụng lệnh git branch -m hoặc git rename. Dưới đây là cách thực hiện:

        -   Chuyển sang branch mà muốn đổi tên bằng cách sử dụng lệnh git checkout <tên branch>. Ví dụ, để chuyển sang branch có tên là feature-A, có thể sử dụng lệnh git checkout feature-A.
        -   Đổi tên branch bằng cách sử dụng lệnh git branch -m <tên mới> hoặc git branch -m <tên cũ> <tên mới>. Ví dụ, để đổi tên branch hiện tại sang feature-B, có thể sử dụng lệnh git branch -m feature-B.
        -   Sau khi đổi tên branch, có thể xác nhận bằng cách sử dụng lệnh git branch để kiểm tra danh sách các branch và xác nhận rằng tên branch đã được thay đổi.

-   Lưu ý rằng khi đổi tên branch, Git sẽ cập nhật tên branch trong repository và tất cả các commit và lịch sử trên branch đó. Nếu đã đẩy branch lên remote repository, cần đẩy các thay đổi mới lên remote repository bằng cách sử dụng lệnh git push --force hoặc git push -f để cập nhật tên branch trên remote repository.

-   Ngoài ra, cũng có thể sử dụng lệnh git branch -m <tên cũ> <tên mới> để đổi tên một branch khác nằm ngoài branch hiện tại.

<a name="gitV.4"></a>

## 4. Thực hành về git branch

-   Thực hành tại web Learn Git Branching
    <img src= images/th6.png>

<a name="gitV.5"></a>

## 5. Git checkout đến commit id

-   Trong Git, có thể sử dụng lệnh git checkout để chuyển đến một commit cụ thể bằng cách sử dụng commit ID hoặc tên nhánh.

-   Để chuyển đến một commit ID cụ thể, cần sử dụng lệnh git checkout <commit ID>. Ví dụ, để chuyển đến commit có ID là abc123, có thể sử dụng lệnh sau:

```
git checkout abc123
```

-   Sau khi thực hiện lệnh này, Git sẽ chuyển đến commit đó và thiết lập thư mục làm việc của bạn để phù hợp với trạng thái của commit đó. Lưu ý rằng bạn sẽ ở trạng thái "detached HEAD" khi chuyển đến một commit cụ thể, điều này có nghĩa là bạn không đang ở trên một nhánh cụ thể nào. Bạn có thể tạo một nhánh mới từ commit đó bằng cách sử dụng lệnh git checkout -b <tên branch>.

-   Để chuyển trở lại branch hiện tại, có thể sử dụng lệnh git checkout <tên branch>. Nếu muốn chuyển đến commit mới nhất trên branch hiện tại, có thể sử dụng lệnh git checkout <tên branch>.

<a name="gitVI"></a>

# VI. Các thao tác liên quan khác:

<a name="gitVI.1"></a>

## 1. Git Merge

-   Trong Git, merge là quá trình hợp nhất các thay đổi từ một branch vào branch khác. Quá trình này cho phép kết hợp các thay đổi từ branch khác để tạo ra một phiên bản mới của repository.

-   Để thực hiện merge trong Git, cần chuyển đến branch mà muốn hợp nhất thay đổi từ branch khác. Sau đó, có thể sử dụng lệnh git merge để thực hiện quá trình merge. Dưới đây là cách thực hiện:

    -   Chuyển đến branch mà muốn hợp nhất thay đổi từ branch khác bằng cách sử dụng lệnh git checkout <tên branch>. Ví dụ, để chuyển đến branch master, có thể sử dụng lệnh git checkout master.
    -   Sử dụng lệnh git merge <tên branch> để hợp nhất các thay đổi từ branch khác vào branch hiện tại. Ví dụ, để hợp nhất các thay đổi từ branch có tên là feature-A, có thể sử dụng lệnh git merge feature-A.
    -   Git sẽ thực hiện merge các thay đổi từ branch feature-A vào branch hiện tại. Nếu có xung đột giữa các thay đổi từ hai branch, Git sẽ yêu cầu giải quyết xung đột trước khi hoàn thành quá trình merge.
    -   Sau khi quá trình merge hoàn tất, có thể thực hiện commit để lưu các thay đổi đã được hợp nhất. Lưu ý rằng nếu đã sử dụng lệnh git merge mà không có xung đột, Git sẽ tự động tạo commit mới cho quá trình merge.

<a name="gitVI.2"></a>

## 2. Git Rebase

-   Trong Git, rebase là quá trình di chuyển các commit từ một branch sang branch khác, hoặc di chuyển các commit trên cùng một branch để đưa chúng lên trên cùng. Khi thực hiện rebase, các commit sẽ được tái áp dụng trên branch mới, và lịch sử commit sẽ trông giống như các commit đã được thực hiện trên branch mới từ đầu.

-   Để thực hiện rebase trong Git, có thể sử dụng lệnh git rebase. Dưới đây là cách thực hiện:

        -   Chuyển đến branch mà muốn rebase bằng cách sử dụng lệnh git checkout <tên branch>. Ví dụ, để chuyển đến branch feature-A, có thể sử dụng lệnh git checkout feature-A.
        - Sử dụng lệnh git rebase <tên branch mới> để di chuyển các commit trên branch hiện tại sang branch mới. Ví dụ, nếu muốn di chuyển các commit trên branch feature-A sang branch master, có thể sử dụng lệnh git rebase master.
        - Git sẽ di chuyển các commit trên branch hiện tại sang branch mới. Nếu có xung đột giữa các commit trên branch hiện tại và branch mới, Git sẽ yêu cầu giải quyết xung đột trước khi tiếp tục quá trình rebase.
        - Sau khi quá trình rebase hoàn tất, có thể thực hiện commit để lưu các thay đổi đã được tái áp dụng. Lưu ý rằng các commit trên branch hiện tại đã được thay đổi và cần đẩy các thay đổi mới của branch hiện tại lên remote repository bằng cách sử dụng lệnh git push --force hoặc git push -f.

-   Lưu ý rằng khi thực hiện rebase, lịch sử commit của branch hiện tại sẽ bị thay đổi và các commit sẽ được tái áp dụng trên branch mới. Việc sử dụng rebase có thể làm cho lịch sử commit của repository trông sạch sẽ hơn, và giúp giảm số lượng commit không cần thiết. Tuy nhiên, cần phải cẩn thận khi sử dụng rebase, vì nó có thể làm mất các thay đổi hoặc xung đột giữa các commit.

<a name="gitVI.3"></a>

## 3. Git Rebase interactive

-   Trong Git, interactive rebase là một công cụ mạnh mẽ cho phép tái sắp xếp, chỉnh sửa và kết hợp các commit trước khi tái áp dụng chúng trên branch mới. Interactive rebase cho phép thực hiện các thao tác như sửa đổi nội dung của commit, chia nhỏ commit thành các commit nhỏ hơn hoặc kết hợp các commit lại với nhau.

-   Để thực hiện interactive rebase trong Git, có thể sử dụng lệnh git rebase -i. Dưới đây là cách thực hiện:

        -   Chuyển đến branch mà muốn rebase bằng cách sử dụng lệnh git checkout <tên branch>. Ví dụ, để chuyển đến branch feature-A, có thể sử dụng lệnh git checkout feature-A.
        -   Sử dụng lệnh git rebase -i <tên branch mới> để mở interactive rebase. Ví dụ, để mở interactive rebase trên branch master, có thể sử dụng lệnh git rebase -i master.
        -   Git sẽ mở một trình soạn thảo văn bản và hiển thị danh sách các commit trên branch hiện tại. Có thể sửa đổi danh sách này để thực hiện các thao tác như sửa đổi nội dung của commit, chia nhỏ commit thành các commit nhỏ hơn hoặc kết hợp các commit lại với nhau. Sau khi đã chỉnh sửa danh sách các commit, có thể lưu và đóng trình soạn thảo.
        -   Sau khi lưu danh sách các commit, Git sẽ bắt đầu tái áp dụng các commit trên branch mới. Nếu có xung đột giữa các commit, Git sẽ yêu cầu giải quyết xung đột trước khi tiếp tục quá trình rebase.
        -   Sau khi quá trình rebase hoàn tất, có thể thực hiện commit để lưu các thay đổi đã được tái áp dụng. Lưu ý rằng các commit trên branch hiện tại đã được thay đổi và cần đẩy các thay đổi mới của branch hiện tại lên remote repository bằng cách sử dụng lệnh git push --force hoặc git push -f.

Lưu ý rằng khi thực hiện interactive rebase, lịch sử commit của branch hiện tại sẽ bị thay đổi và các commit sẽ được tái áp dụng trên branch mới. Việc sử dụng interactive rebase có thể giúp giảm số lượng commit không cần thiết và làm cho lịch sử commit của repository trông sạch sẽ hơn. Tuy nhiên, cần phải cẩn thận khi sử dụng interactive rebase, vì nó có thể làm mất các thay đổi hoặc xung đột giữa các commit.

<a name="gitVI.4"></a>

## 4. Git Rebase khi remote có cập nhật mới

-   Khi thực hiện rebase trên một branch và remote repository có cập nhật mới, cần phải cẩn thận để tránh xung đột và mất dữ liệu.

-   Khi remote repository có cập nhật mới, thường có những thay đổi trên remote repository mà chưa có trên branch hiện tại của mình. Nếu thực hiện rebase trên branch hiện tại trong trường hợp này, Git sẽ ghi đè các thay đổi mới từ remote repository và có thể khiến mất dữ liệu.

-   Để tránh xung đột và mất dữ liệu khi remote repository có cập nhật mới, có thể thực hiện một số bước sau đây:

        -   Chuyển đến branch mà muốn rebase bằng cách sử dụng lệnh git checkout <tên branch>.
        -   Sử dụng lệnh git fetch để lấy các thay đổi mới từ remote repository.
        -   Sử dụng lệnh git rebase -i <tên branch mới> để mở interactive rebase.
        -   Trong trình soạn thảo văn bản, sửa đổi danh sách các commit để tránh xung đột với các thay đổi mới từ remote repository. Có thể chia nhỏ các commit của mình thành các commit nhỏ hơn và di chuyển chúng để tránh xung đột.
        -   Sau khi lưu danh sách các commit, Git sẽ bắt đầu tái áp dụng các commit trên branch mới. Nếu có xung đột giữa các commit, Git sẽ yêu cầu giải quyết xung đột trước khi tiếp tục quá trình rebase.
        -   Sau khi quá trình rebase hoàn tất, sử dụng lệnh git push --force để đẩy các thay đổi mới của branch hiện tại lên remote repository. Lưu ý rằng sử dụng --force có thể thay đổi lịch sử commit trên remote repository, vì vậy cần phải cẩn thận và đảm bảo rằng không ai khác đang làm việc trên remote repository cùng lúc với bạn.

Lưu ý rằng khi thực hiện rebase khi remote repository có cập nhật mới, bạn cần phải cẩn thận để tránh xung đột và mất dữ liệu. Nên luôn cập nhật branch hiện tại của mình trước khi thực hiện rebase và đảm bảo rằng không ai khác đang làm việc trên remote repository cùng lúc với bạn.

<a name="gitVI.5"></a>

## 5. Git Cherry-pick

-   Trong Git, cherry-pick là một công cụ cho phép áp dụng một commit cụ thể từ một branch sang một branch khác mà không cần phải tái áp dụng toàn bộ lịch sử commit của branch đó. Với cherry-pick, có thể chọn các commit cụ thể để áp dụng trên branch hiện tại một cách độc lập.

-   Để thực hiện cherry-pick trong Git, có thể sử dụng lệnh git cherry-pick. Dưới đây là cách thực hiện:

        -   Chuyển đến branch muốn áp dụng commit bằng cách sử dụng lệnh git checkout <tên branch>.
        -   Sử dụng lệnh git log để hiển thị danh sách các commit trên branch khác muốn áp dụng.
        -   Sao chép mã hash của commit muốn áp dụng.
        -   Sử dụng lệnh git cherry-pick <mã hash> để áp dụng commit đó trên branch hiện tại.
        -   Git sẽ áp dụng commit đó trên branch hiện tại và tạo ra một commit mới với nội dung tương tự như commit gốc. Nếu có xung đột giữa commit đã áp dụng và các commit khác trên branch hiện tại, Git sẽ yêu cầu giải quyết xung đột trước khi tiếp tục quá trình cherry-pick.

Lưu ý rằng khi thực hiện cherry-pick, commit đã áp dụng sẽ được tạo ra một commit mới trên branch hiện tại và không có liên kết với commit gốc trên branch khác. Nếu muốn áp dụng một số commit từ branch khác sang branch hiện tại và giữ liên kết với branch khác, có thể sử dụng rebase.

Cherry-pick là một công cụ hữu ích trong quá trình quản lý lịch sử commit của Git, cho phép áp dụng các thay đổi cụ thể mà không cần phải tái áp dụng toàn bộ lịch sử commit của branch đó. Tuy nhiên, cần phải cẩn thận khi sử dụng cherry-pick, vì nó có thể làm mất các thay đổi hoặc tạo ra xung đột giữa các commit.

<a name="gitVI.6"></a>

## 6. Pull và Push

-   Trong Git, pull và push là hai lệnh quan trọng để tương tác với remote repository và đồng bộ hóa các thay đổi giữa local repository và remote repository.

    -   git pull: Là lệnh để lấy các thay đổi mới nhất từ remote repository và áp dụng chúng trên local repository. Lệnh này tương đương với việc thực hiện git fetch (lấy các thay đổi mới nhất từ remote repository) và git merge (áp dụng các thay đổi đó trên local repository). Khi thực hiện git pull, Git sẽ tự động tìm kiếm và áp dụng các thay đổi mới nhất từ remote repository lên branch hiện tại của. Nếu có xung đột giữa các thay đổi trên remote repository và local repository, Git sẽ yêu cầu giải quyết xung đột trước khi tiếp tục quá trình pull.

    -   git push: Là lệnh để đẩy các thay đổi từ local repository lên remote repository. Khi thực hiện git push, Git sẽ gửi các thay đổi đã được commit từ local repository lên remote repository. Nếu remote repository có các thay đổi mới hơn, Git sẽ từ chối đẩy và yêu cầu lấy các thay đổi mới nhất từ remote repository trước khi tiếp tục quá trình push.

Lưu ý rằng khi thực hiện git pull và git push, cần phải đảm bảo rằng đang làm việc trên branch đúng và đã commit các thay đổi của mình trước khi thực hiện các lệnh này. Nếu thực hiện git push mà không có các thay đổi mới từ local repository, Git sẽ không đẩy bất kỳ thay đổi nào lên remote repository. Nếu thực hiện git pull và có xung đột giữa các thay đổi trên remote repository và local repository, cần phải giải quyết xung đột trước khi tiếp tục quá trình pull.

Tóm lại, git pull và git push là hai lệnh quan trọng trong quá trình tương tác với remote repository và đồng bộ hóa các thay đổi giữa local repository và remote repository. Cần phải cẩn thận khi sử dụng các lệnh này để đảm bảo rằng các thay đổi của được đồng bộ hóa đúng cách và không có xung đột giữa các thay đổi từ các người dùng khác.

<a name="gitVI.7"></a>

## 7. Tuỳ chọn force trong git

-   Tùy chọn force trong Git được sử dụng để ép buộc các thay đổi trên local repository được đẩy lên remote repository mà không cần phải cập nhật local repository với trạng thái mới nhất của remote repository trước đó. Khi sử dụng tùy chọn force, Git sẽ ghi đè toàn bộ lịch sử commit của remote repository bằng lịch sử commit trên local repository.

-   Có hai lựa chọn force trong Git:

        -   --force: Lựa chọn này sẽ ép buộc các thay đổi từ local repository được đẩy lên remote repository mà không cần phải cập nhật local repository với trạng thái mới nhất của remote repository trước đó. Nếu remote repository có các thay đổi mới hơn, các thay đổi này sẽ bị ghi đè bởi thay đổi từ local repository.
        -   --force-with-lease: Lựa chọn này cũng sử dụng để ép buộc các thay đổi từ local repository được đẩy lên remote repository, nhưng nó sẽ kiểm tra xem có thay đổi nào mới hơn trên remote repository trước khi đẩy các thay đổi từ local repository lên. Nếu có thay đổi mới hơn trên remote repository, Git sẽ từ chối đẩy và yêu cầu cập nhật local repository với trạng thái mới nhất của remote repository trước khi tiếp tục quá trình đẩy các thay đổi.

Lưu ý rằng sử dụng tùy chọn force trong Git có thể gây ra mất dữ liệu và làm thay đổi lịch sử commit trên remote repository. Nếu sử dụng tùy chọn này, hãy đảm bảo rằng đang làm việc trên branch đúng và không có ai khác đang làm việc trên remote repository cùng lúc với.

Tóm lại, tùy chọn force trong Git được sử dụng để ép buộc các thay đổi từ local repository được đẩy lên remote repository mà không cần phải cập nhật local repository với trạng thái mới nhất của remote repository trước đó. Tuy nhiên, cần phải cẩn thận khi sử dụng tùy chọn này để tránh mất dữ liệu và làm thay đổi lịch sử commit trên remote repository.

<a name="gitVII"></a>

# VII. Các thao tác với git remote

-   Trong Git, các thao tác với remote cho phép tương tác với remote repository và đồng bộ hóa các thay đổi giữa local repository và remote repository. Sau đây là một số thao tác phổ biến với remote trong Git:

    -   Add remote: Thêm một remote repository mới bằng lệnh git remote add <remote name> <remote URL>. Lệnh này sẽ thêm một remote repository mới với tên được chỉ định và URL của remote repository. Ví dụ: git remote add origin https://github.com/hieuminhvuu/git_training.git.

    -   Rename remote: Đổi tên một remote repository bằng lệnh git remote rename <old name> <new name>. Lệnh này sẽ đổi tên remote repository từ tên cũ thành tên mới được chỉ định. Ví dụ: git remote rename origin upstream.

    -   Update remote: Cập nhật thông tin của remote repository bằng lệnh git remote update. Lệnh này sẽ lấy các thay đổi mới nhất từ remote repository về local repository, nhưng không áp dụng các thay đổi này trên local repository.

    -   Prune remote branch: Xóa các branch không còn tồn tại trên remote repository bằng lệnh git remote prune <remote name>. Lệnh này sẽ xóa các branch không còn tồn tại trên remote repository được chỉ định khỏi local repository.

Lưu ý rằng trong Git, remote repository có thể được liên kết với nhiều local repository, và một local repository có thể được liên kết với nhiều remote repository. Khi sử dụng các thao tác với remote, hãy đảm bảo rằng đang làm việc với remote repository đúng và không ghi đè lên các thay đổi của các thành viên trong nhóm khác.

<a name="gitVIII"></a>

# VIII. Các thao tác với Stash

<a name="gitVIII.1"></a>

## 1. Tổng quan về git stash

-   Trong Git, stash là một tính năng mạnh mẽ cho phép tạm thời lưu trữ các thay đổi không được commit trên local repository. Khi sử dụng stash, các thay đổi này sẽ được lưu trữ tạm thời trong một stack stash để có thể chuyển sang làm việc trên task khác mà không cần commit những thay đổi đó. Các thao tác phổ biến với stash trong Git bao gồm:

    -   Lưu trữ các thay đổi không được commit bằng lệnh git stash. Lệnh này sẽ lưu trữ các thay đổi trên local repository vào một stash tạm thời. Nếu muốn lưu trữ stash với một message, có thể sử dụng lệnh git stash save "message".

    -   Xem danh sách các stash đã lưu trữ bằng lệnh git stash list. Lệnh này sẽ hiển thị danh sách các stash đã lưu trữ trên local repository.

    -   Áp dụng các thay đổi từ stash mới nhất bằng lệnh git stash apply. Lệnh này sẽ áp dụng các thay đổi từ stash mới nhất lưu trữ trên local repository.

    -   Xóa stash mới nhất bằng lệnh git stash drop. Lệnh này sẽ xóa stash mới nhất đã lưu trữ trên local repository.

    -   Xóa toàn bộ stash bằng lệnh git stash clear. Lệnh này sẽ xóa toàn bộ stash đã lưu trữ trên local repository.

    -   Kiểm tra nội dung của stash bằng lệnh git stash show. Lệnh này sẽ hiển thị nội dung của stash mới nhất.

Khi sử dụng stash, cũng có thể sử dụng nhiều tùy chọn khác nhau để lưu trữ các thay đổi, như git stash pop để áp dụng stash mới nhất và xóa nó sau đó, git stash branch để tạo một branch mới từ stash, hoặc git stash drop <stash id> để xóa một stash cụ thể.

Lưu ý rằng khi sử dụng stash, các thay đổi không được commit sẽ được lưu trữ tạm thời trên local repository. Nếu không áp dụng chúng trở lại sau này, các thay đổi này sẽ bị mất khi xóa stash hoặc khi xóa branch được tạo ra từ stash.

<a name="gitVIII.2"></a>

## 2. git stash list

-   Trong Git, lệnh git stash list được sử dụng để hiển thị danh sách các stash đã lưu trữ trên local repository. Khi sử dụng lệnh này, Git sẽ hiển thị một danh sách các stash đã được đánh số thứ tự và được lưu trữ tạm thời trên local repository. Mỗi stash được liệt kê với một message mô tả nội dung của stash đó.

-   Cú pháp sử dụng lệnh git stash list như sau:

```
git stash list
```

Kết quả sẽ có dạng:

```
apache
stash@{0}: WIP on feature-branch: c3f3b6a Add new feature
stash@{1}: WIP on master: 2a45bf7 Fix bug
stash@{2}: WIP on dev: 5d8b1e0 Update README
```

-   Trong ví dụ trên, danh sách bao gồm 3 stash, được đánh số thứ tự là 0, 1 và 2. Stash đánh số 0 và 1 được lưu trữ trên các branch feature-branch và master tương ứng, trong khi stash đánh số 2 được lưu trữ trên branch dev. Nội dung của mỗi stash được miêu tả bằng message tương ứng.

Lưu ý rằng các stash được đánh số thứ tự theo thứ tự ngược lại, với stash mới nhất được đánh số là 0.

<a name="gitVIII.3"></a>

## 3. git stash clear

Trong Git, lệnh git stash clear được sử dụng để xóa toàn bộ danh sách các stash đã lưu trữ trên local repository. Khi sử dụng lệnh này, tất cả các stash hiện có trên local repository sẽ bị xóa và không thể khôi phục lại.

Cú pháp sử dụng lệnh git stash clear như sau:

```
git stash clear
```

Khi sử dụng lệnh này, Git sẽ xóa toàn bộ danh sách các stash đã lưu trữ trên local repository và không hiển thị bất kỳ thông báo hay xác nhận nào. Do đó, hãy đảm bảo rằng đã sao lưu và xác nhận rằng không còn bất kỳ stash quan trọng nào trên local repository trước khi sử dụng lệnh này.

Lưu ý rằng việc xóa các stash sẽ không ảnh hưởng đến các commit đã được thực hiện trên local repository. Nếu muốn xóa một stash cụ thể, có thể sử dụng lệnh git stash drop <stash id> để xóa stash có đánh số thứ tự là stash id.

<a name="gitVIII.4"></a>

## 4. git stash --help

-   Trong Git, lệnh git stash --help được sử dụng để hiển thị trợ giúp về các tùy chọn và cách sử dụng của lệnh stash. Khi sử dụng lệnh này, Git sẽ hiển thị một trang trợ giúp với các tùy chọn, cú pháp và các ví dụ về cách sử dụng lệnh stash.

-   Cú pháp sử dụng lệnh git stash --help như sau:

```
git stash --help
```

-   Kết quả trả về sẽ hiển thị một trang trợ giúp về lệnh stash, bao gồm các phần sau:

    -   Cú pháp: mô tả cú pháp của lệnh stash, bao gồm các tùy chọn và tham số.

    -   Tùy chọn: liệt kê các tùy chọn có thể được sử dụng với lệnh stash, bao gồm các tùy chọn thông dụng như --message (để thêm một message cho stash), --patch (để tạo stash chỉ với các thay đổi được chọn), --all (để lưu trữ tất cả các thay đổi, bao gồm cả các file chưa được theo dõi), vv.

    -   Mô tả: cung cấp mô tả chi tiết về cách sử dụng lệnh stash, bao gồm các ví dụ về cách sử dụng lệnh stash trong các tình huống khác nhau.

    -   Tham số: liệt kê các tham số có thể được sử dụng với lệnh stash, bao gồm các tham số thông dụng như <stash> (để xem chi tiết của một stash cụ thể), <branch> (để tạo một branch mới từ stash), vv.

Khi cần trợ giúp về cách sử dụng lệnh stash hoặc cần xem các tùy chọn của lệnh stash, lệnh git stash --help là một công cụ hữu ích để giúp làm điều đó.
