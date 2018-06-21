# Hướng dẫn chạy service nhận diện khuôn mặt từ docker image 

1. Tải image từ [đây](https://drive.google.com/open?id=1TNBD2Hddr1YF-TLwfvrDAIjduKeNDjZT).
2. Tải docker tại [đây](https://www.docker.com/community-edition) và cài đặt docker.
3. Di chuyển đến thư mục chứa image vừa tải và mở cửa sổ command line (hoặc powershell đối với hđh window)
4. Chạy lệnh:    
    ```
    docker load -i face_demo.tar
    ```
5. Sau khi quá trình cài đặt image hoàn thành, chạy lệnh `docker image ls`, sẽ thấy có repository `face_demo`.
6. Khởi động container chạy service:
    ```
    docker run -p 11111:11111 -d --name face_recognition face_demo
    ```
    Quá trình khởi động service sẽ mất 1-2 phút.
7. Chạy lệnh `docker container ls -a` sẽ thấy container có `NAMES` là `face_recognition` có `STATUS` `Up ...`. Vào trang `localhost:11111` trên trình duyệt sẽ thấy trang web FACE COMPARES
8. Sau lần cài đặt đầu tiên, khi cần chạy service, chỉ cần chạy lệnh:
    ```
    docker container start face_recognition
    ```
9. Để tắt service, chạy lệnh:
    ```
    docker container stop face_recognition
    ```
    


