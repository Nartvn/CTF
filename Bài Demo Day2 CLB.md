
bài Demo buổi học ctf day2

lấy hết file cờ ra ghép lại thành 1 file theo thứ tự, decode base64 sẽ ra được file định dạng png đó là flag.

code python ghép lại
```python=
# Tên các file cần ghép
file_count = 145  # Số lượng file từ fl4g_0.bin đến fl4g_144.bin
output_file = "merged_fl4g.bin"  # Tên file kết quả

# Ghép các file
with open(output_file, "wb") as merged_file:
    for i in range(file_count):
        file_name = f"fl4g_{i}.bin"
        try:
            with open(file_name, "rb") as part_file:
                merged_file.write(part_file.read())
            print(f"Đã ghép {file_name}")
        except FileNotFoundError:
            print(f"Không tìm thấy {file_name}, bỏ qua file này.")

```

được flag:

![image](https://hackmd.io/_uploads/SyF8fNWbkl.png)
