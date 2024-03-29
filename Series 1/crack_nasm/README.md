# CRACK_NASM
## Task
Đầu tiên, em chạy thử file thực thi để xem chương trình này làm gì.  
```
└─$ ./CrackMe_ASM
Flag : 31245fa
you are wrong , try again !
```
> Tìm flag bí mật.

## Solution
Tiếp theo, để biết được các quy luật mà chương trình sử dụng để so sánh, em tiến hành mở file bằng công cụ **IDA Pro**.  
Nhưng trước tiên, em dùng câu lệnh `file` trên Linux để kiểm tra xem file thực thi này được compile bởi một máy có kiến trúc gì (32bit hay 64bit).
```
└─$ file CrackMe_ASM
CrackMe_ASM: ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), statically linked, not stripped
```
Từ kết quả trên, em biết được file này là file 32bit, và em bắt đầu chạy **IDA Pro** phiên bản 32bit để xem hợp ngữ của chương trình.

Trên **IDA**, hợp ngữ của chương trình như sau:  
![](https://github.com/datthinh1801/NT209.L21.ANTN-Challenges/blob/main/crack_nasm/crach_nasm_ida.png)

Dễ dàng nhận thấy những ký tự rất *kỳ lạ* kia là `S3CrE+Fl4G!`. Em liền test thử chuỗi này.  
```
└─$ ./CrackMe_ASM
Flag : S3CrE+Fl4G!
you are correct !  
```
> Chuỗi này chính là `flag` bí mật. Vậy kết quả là `S3CrE+Fl4G!`.
