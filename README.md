# Reflection

## Hello Minikube

1. Compare logs

    Sebelum
    ![image1](/img/image1.png)

    Sesudah membuka aplikasi beberapa kali
    ![image2](/img/image2.png)

    Logs menunjukkan timestamp dari get request pada aplikasi, logs tersebut bertambah setiap saat aplikasi tersebut di buka.

2. Tujuan dari menggunakan -n adalah untuk memperlihatkan pods dan service pada namespace tertentu, ketika kita tidak menggunakan -n kube-system, maka pods dan service yang diperlihatkan hanyalah dari namespace `default` sehingga tidak memunculkan pods/service yang secara eksplisit telah dibuat yang di mana namespacenya adalah `kube-system`.

## Rolling Update & Kubernetes Manifest File

1. Perbedaan dari rolling update dengan recreate deployment adalah, rolling update melakukan update pada app dengan melakukan penambahan dari yang sudah ada hingga ke versi terbarunya sedangkan pada recreate deployment app akan di delete semua dan dilakukan create ulang dari awal mengikuti template dari version terbarunya.

2. Berikut adalah cara saya mengganti strategy menjadi recreate deployment

    ![image3](/img/image3.png)
    Pada awalnya yaml pada app petclinic akan diganti valua strategynya dari rollingUpdate menjadi recreate

    ![image4](/img/image4.png)
    Modifikasi tersebut dilakukan melalui notepad

    ![image5](/img/image5.png)
    Dapat terlihat sekarang konfigurasi sudah menggunakan recreate deployment

    ![image6](/img/image6.png)
    Disini akan dicoba untuk melakukan update ke versi sebelumnya dan terlihat bahwa pods aplikasi dilakukan terminasi semua

    ![image7](/img/image7.png)
    Setelah itu status menunjukkan container sedang dibuat, hal ini menunjukkan bahwa strategi update berhasil menggunakan recreate deployment.

3. ![image8](/img/image8.png)
Perintah tersebut dijalankan untuk mendapatkan manifest files.  

4. Menyiapkan manifest files memberikan keuntungan dalam memberikan konfigurasi yang konsisten pada aplikasi kita serta memberikan fasilitas untuk pengelolaan versi, riwayat perubahan, memudahkan kolaborasi tim, dan integrasi dengan tools CI/CD. 