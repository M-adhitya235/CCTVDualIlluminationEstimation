# Peningkatan Kualitas Pencahayaan Citra CCTV Jalan Raya Di Malam Hari Menggunakan Dual Illumination Estimation

Penelitian ini menggunakan metode Dual Illumination Estimation untuk meningkatkan pencahayaan dari citra CCTV jalan raya di malam hari yang memiliki kondisi pencahayaan rendah dan tidak merata. Selain itu, dalam penelitian ini juga membandingkan dengan metode konvensional seperti Histogram Equalization dan Contrast Stretching.


# Dual Illumination Estimation

#Parameter 
#default values
"be": 1.0,           # Bobot peningkatan kecerahan (brightness)
"bs": 1.0,           # Bobot peningkatan kejenuhan warna (saturation)
"bc": 1.0,           # Bobot peningkatan kontras
"size": 15,          # Ukuran kernel Gaussian untuk meratakan pencahayaan lokal
"sigma": 3,          # Standar deviasi Gaussian, mengatur tingkat blur
"gamma": 0.6,        # Nilai gamma untuk mengoreksi kecerahan secara global
"lamda": 0.15,       # Nilai untuk mengatur kehalusan pencahayaan (regularisasi)  
"eps": 1e-3,         # Nilai kecil untuk mencegah pembagian dengan nol
"neighbour_dist": 1  # Jarak antar piksel tetangga yang digunakan dalam perhitungan spasial

Notes :
Parameter dapat disesuaikan kebutuhan.


# Memanggil Fungsi Dual Illumination Estimation
process_video(input_path, output_path, image_config, save_frames_dir=None)

Contoh Penggunaan:
process_video('/content/Kebunsayur_Resize.mp4', '/content/kebunsayur_dual.mp4', image_config, save_frames_dir='/content/dual/frame_ks')


# Histogram Equalization (HE)

# Memanggil Fungsi HE
process_video_he(input_path, output_path, save_frames_dir=None)

Contoh Penggunaan:
process_video_he("/content/Kebunsayur_Resize.mp4", "/content/KebunSayur_HE.mp4", save_frames_dir='/content/framehe_ks')


# Contrast Stretching dengan Percentile

# Fungsi Contrast Stretching 
contrast_stretch_percentile(img, low_percentile=5, high_percentile=95), 

Notes:
Bisa disesuaikan kebutuhan cth. low=2, high=98 dsb.

# Memanggil Fungsi Contrast Stretching
video_contrast_stretch_percentile(input_path, output_path, save_frames_dir=None)

Contoh Penggunaan:
video_contrast_stretch_percentile("/content/Kebunsayur_Resize.mp4","/content/KebunSayur_CS.mp4", save_frames_dir="/content/framecs_ks")
