# Forensics - File Detail
## 1. Enhance (PicoCTF)

### Đề bài

![enhance](https://github.com/KongSugoi/Forensics-File-Detail-WU/blob/main/Folder%20Solve%20Picture/enhance0.png)

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

## 6. MilkSlap (PicoCTF)

### Đề bài

![milkslap]()

<p> Bài này cho chúng ta một cái web đổ sữa vào 1 người nào đó <p>

![milkslap]()

<p> Vì đây là bài dạng Forensics nên sẽ không có lỗ hổng như Web - exploitation, vậy nên ta sẽ phải tìm hiểu trong web này có những source gì có thể khai thác. Ta mở source của web và thấy được có 1 file có thể sử dụng là concat_v.png <p>

![milkslap]()

<p> Sau khi kiểm tra dạng file, các header và metadata thì file này không thuộc dạng File Carving hay File Detail bình thường, mà sẽ hơi xu hướng dạng Steganography nhưng vẫn cơ bản, vậy nên ta sẽ dung PowerShell hoặc cho vào Ubuntu sử dụng zsteg để giải mã các đoạn text ẩn trong ảnh <p>

![milslap]()

```Flag: picoCTF{imag3_m4n1pul4t10n_sl4p5} ```

## 7. Extensions (PicoCTF)

### Đề bài 

![extension]()

<p> Đề cho ta một file txt rất bình thường. Mở file lên ta thấy ngay ở đoạn đầu có dấu hiệu của 1 file PNG <p>

![extension]()

<p> Đổi lại đuôi file thành png ta có ngay flag <p>

![extension]()

```Flag: picoCTF{now_you_know_about_extensions}```

## 8. So Meta (PicoCTF)

### Đề bài 

![someta]()

<p> Đề bài cho ta 1 file ảnh, dựa theo đề bài " Meta", mở file dưới dạng Notepad và thấy ngay flag ở cuối file <p>

![someta]()

```Flag: picoCTF{s0_m3ta_fec06741}```

## 9. What lies within (PicoCTF)

### Đề bài 

![whatlies]()

<p> Đề bài cho 1 cái ảnh và nó hỏi có gì ẩn giấu trong đó, đối với ảnh, ta lại sử dụng tool zsteg để kiểm tra thôi. Và thế là ta thấy ngay flag <p>

![whatlies]()

```Flag: picoCTF{h1d1ng_1n_th3_b1t5}```

## 10. like1000 (PicoCTF)

### Đề bài

![1000]()

<p> Đề cho ta 1 file .tar tương tự dạng file .zip .rar là 1 dạng file nén, khi mở thử file đó ra ta thấy file có tên 999.tar <p>

![1000]()

<p> Điều này chứng tỏ, mình phải mở được tất cả (hoặc có thể là 1 vài) file để có thể lấy được flag. (có thể nó ở 1 chỗ bất kỳ, nhưng hãy tin tưởng là nó ở file cuối cùng đi) <p>

<p> Để nó vào Ubuntu và bắt đầu dùng code để mở file. Để mở file tar, ta dùng code "tar xvf tên file" <p>

![1000]()

<p> Giờ thì ta sử dụng 1 đoạn code lặp để có thể mở liên tục file .tar, vì ta biết được quy luật của nó sẽ là 1000->999->998->997..... nên ta sẽ code đoạn mã như sau <p>

![1000]()

<p> Sau khi extract hết tất cả file, ta có được 1 bức ảnh flag.png <p>

![1000]()

<p> Tìm flag.png mở ra thì chính là flag luôn <p>

``` Flag: picoCTF{l0t5_0f_TAR5}```

## 11. MacroHard WeakEdge (PicoCTF)

### Đề bài 

![fun]()

<p> Nó cho ta 1 file dạng pptm (dạng powerpoint) nhưng khi mở thì không thể mở được, điều này chứng tỏ ta phải chuyển sang đúng định dạng file. Mở file bằng Notepad hoặc thả vào ubuntu sử dụng binwalk <p>

![fun]()

<p> Vậy là ta biết được đây là 1 file zip bị đổi tên. Và ta có thấy được trong 1 vị trí folder có thể sẽ có flag "ppt/slideMasters/hidden" <p>

<p> Tới vị trí file đó, mở lên thì thấy được 1 đoạn mã <p>

![fun]()

<p> Nhìn là biết đây là mã Base64 vậy nên ta decode luôn và có được flag <p>

``` Flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}```


## 12. Image File Format Analysis (UIT CTF)

### Đề bài 

#### Bài này chỉ có 1 file, đề của trường UIT mà mình clone được

<p> Cho file vào ubuntu và sử dụng binwalk file, ta có được kết quả chứa 1 file PDF và 1 file JPEG, nhưng ảnh này lại không mang định dạng .zip vậy nên ta không thể đổi đuôi file thành zip và giải nén được <p>

![format]()

<p> Vậy ta biết được đây là 1 file ẩn sâu trong ảnh. Vậy nên ta sẽ sử dụng câu lệnh " binwalk --dd='.*' " (không tính ngoặc kép nha) để extract file bất chấp bị khóa khả năng archive <p>

![format]()

<p> Ta có được file 123.jpg_extracted <p>

<p> Mở file ta có 1 ảnh 0.jpg và 1 file 2E11E (file này nhìn hình có vẻ như định dạng pdf nên ta đổi tên file là pdf) <p>

![format]()

<p> Xem slide và đến slide 25 ta thấy được flag ở trên góc <p>

![format]()

``` Flag: flag{m0r3_v4lu4bl3_th4n_y0u_th1nk} ```
