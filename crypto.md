# Just For Fun
Đề bài cho mình một file Just4Fun.rar :
![image](https://user-images.githubusercontent.com/101586892/218304582-86f210f3-be30-426f-adcc-40b8b073bc2e.png)
Mở file crypto2.py ta thấy được source :
'''
import string
import random
flag='this is fake flag'
ciphertext=''
alphabet=[]
flag_array=[]
check=[]
key=[]
for i in range(97,123):
alphabet.append(chr(i))
key.append(chr(i))

for i in range(len(flag)):
    flag_array.append(flag[i])
    check.append(1)

random.shuffle(key)
key_string=""
for i in key:
    key_string+=i
for i in range(len(alphabet)):
    for j in range(len(flag)):
        if check[j]:
            if alphabet[i]==flag_array[j]:
                check[j]=0
                flag_array[j]=key[i]
for i in flag_array:
    ciphertext+=i
print(ciphertext)
'''

Dựa theo gợi ý ở phần mô tả "vũ điệu lắc hông" và source thì mình biết đây là loại mật mã **Monoalphabetic**

Mở file **cipher.txt** ta có dòng ciphertext : limh_xwd_oqkl_zndn_ieclithkqv
Mình sử dụng tool https://www.boxentriq.com/code-breaking/cryptogram 
Mình thấy một từ giống từ alphabetic nên mình bắt đầu đoán 
![image](https://user-images.githubusercontent.com/101586892/218304976-8396aa6c-7bf3-4b9c-b6a4-42ea8af050ce.png)
Tới đây thì mình dựa tên đề bài để đoán flag 
![image](https://user-images.githubusercontent.com/101586892/218305065-11ccf27e-3442-4827-be14-27876686507c.png)
![image](https://user-images.githubusercontent.com/101586892/218305093-cea36aa5-609b-4ce2-b8cb-e6d8550c4924.png)
Và mình đã được flag: 
**PISCTF{have_fun_with_mono_alphabetic}**
 
