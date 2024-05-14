# Reflection

## Hello Minikube

1. Compare logs

    Sebelum
    ![image1](/img/image1.png)

    Sesudah membuka aplikasi beberapa kali
    ![image2](/img/image2.png)

    Logs menunjukkan timestamp dari get request pada aplikasi, logs tersebut bertambah setiap saat aplikasi tersebut di buka.

2. Tujuan dari menggunakan -n adalah untuk memperlihatkan pods dan service pada namespace tertentu, ketika kita tidak menggunakan -n kube-system, maka pods dan service yang diperlihatkan hanyalah dari namespace `default` sehingga tidak memunculkan pods/service yang secara eksplisit telah dibuat yang di mana namespacenya adalah `kube-system`.