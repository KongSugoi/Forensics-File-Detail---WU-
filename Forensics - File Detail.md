# Forensics - File Detail
## 1. Enhance (PicoCTF)

### Đề bài

![enhance]()

<p>Chúng ta nhận được 1 file có dạng svg, 1 dạng file khá là lạ. Trước tiên ta thử mở file này lên, thì biết được đây là 1 file liên quan tới web.<p>

![enhance]()

<p> Thử F12 xem nó ra cái gì (hoặc có thể Open with Notepad từ cái file ban đầu)<p>
<p> Vào Source và ta thấy có 1 đoạn chữ gì đó bị cắt thành nhiều đoạn ngắn, được ẩn trong thẻ "tspan"<p>

![enhance]()

<p>Ghép các đoạn đó lại với nhau ta được 1 flag rõ ràng: <p>

```Flag: picoCTF{3nh4nc3d_d0a757bf}``` *(Nhớ xóa dấu cách và tự làm trên acc PicoCTF của mình nhé)*

## 2. Information (PicoCTF)

### Đề bài 

![information]()

<p> Chúng ta nhận được 1 ảnh con meo meo ngồi bên cạnh máy tính, nhìn đoạn code trên máy tính thì mình chắc chắn là chả dùng được gì ở đây, vậy nên chúng ta cùng xem xét đến các dữ liệu của ảnh. <p>

<p> Mở ảnh bằng Notepad thôi <p>

![information]()

<p> Ồ, ta thấy được 1 đoạn mã rất khả nghi nha (nhận biết đoạn mã nhờ kinh nghiệm làm bài + học Crypto sẽ thấy rất quen mắt) <p>

![information]()

<p> Dịch đoạn mã từ base64 ra ASCII ta được flag <p>

```Flag: picoCTF{the_m3tadata_1s_modified}```

## 3. Glory of Garden (PicoCTF)

### Đề bài

![garden]()

<p> Chúng ta nhận được 1 bức ảnh khu vườn, không có gì khả nghi ở trong bức ảnh này cả, hãy thử mở nó bằng Notepad nào <p>

<p> Kiểm tra tất cả các thứ trong phần Notepad này thì thấy ở cuối có ngay flag <p>

![garden]()

```Flag: picoCTF{more_than_m33ts_the_3y3657BaB2C}```

## 4. Lookey Here (PicoCTF)

### Đề bài

![lookey]()

<p> Chúng ta được 1 file văn bản được để với dạng txt, mở ra thì là 1 bản gì gì đó như bài Thánh Ca của đạo Thiên Chúa ??? <p> 

<p> Chỉ với dữ kiện duy nhất là file này thì ta có thể suy luận ra, flag chỉ có thể ở trong đây được thôi <p>

<p> Dùng Ctrl+F tìm chữ Pico thôi, thấy ngay flag <p>

![lookey]()

```Flag: picoCTF{gr3p_15_@w3s0m3_4c479940}```

## 5. Who is it (PicoCTF)

### Đề bài

![whoisit]()

<p> Đề bài là cho 1 file email, nhưng người gửi là mạo danh, chúng ta cần phải tìm tên thật của người đó và tên thật đó chính là flag <p>

<p> Đối với những dạng bài như này chúng ta sẽ thường dùng whois để tìm kiếm thông tin người gửi, mở email và lấy thông tin người gửi sau đó vào <p>

[whois](https://whois.whoisxmlapi.com/)

<p> Ta được những thông tin vô tác dụng <p> 

[whois infor](https://whois.whoisxmlapi.com/lookup-report/ax5D3ejj26)

<p> Điều này chứng tỏ thông tin này đã bị ẩn đi để không ai nhìn thấy (thực ra thì sử dụng mail onionmail.com thì ta có thể hiểu được rồi) <p>

<p> Đọc thử hint của bài nó bảo <p>

![whoisit]()

<p> Ồ, vậy là ta không tìm được bằng mail, chúng ta phải sử dụng IP của mail này, xác định được IP địa điểm gửi, ta có thể xác định được danh tính của người này. Vậy thì dễ thôi, ta mở file email này bằng Notepad <p>

![whoisit]()

<p> Trong một chuỗi thông tin nhận được ta thấy có 1 địa chỉ IP rất đáng ngờ, đồng thời ở sau đó có đoạn thông tin "permitted" nên có thể chắc chắn được điều này <p>

![whoisit]()

<p> Ta tìm trên web <p>

[whois](https://www.whois.com/whois/)

<p> Và ta tìm được tên của chính chủ <p>

![whoisit]()

```Flag: picoCTF{WilhelmZwalina}```

6. 