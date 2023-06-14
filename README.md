# food-recommender
Back-end untuk menghasilkan rekomendasi berdasarkan karakteristik kegemaran bahan makanan serta tingkat kepedasan pengguna

Inbound port: 8000 (FastAPI)

Route yang tersedia:

'/predict' (POST): menerima data user (terutama field "spiceLevel" dan "likedIngredients") dan mengembalikan uid dan list food_id hasil rekomendasi


# Development Setup
Buka terminal dan ubah direktori tempat dimana ingin meng-git clone repository ini

## Clone into your local directory with 
```
git clone https://github.com/khalidrizki01/food-recommender.git
cd food-recommender/api
```

## Buat dan aktifkan virtual environment
Ada dua pilihan dalam membuat virtual environment, yakni dengan conda atau dengan venv
### Apabila menggunakan conda
```
conda create --name food-recommender
conda activate food-recommender
```
### Apabila menggunakan venv
```
python -m venv food-recommender-env
```
Dengan venv, ada dua cara untuk mengaktifkan environment, yakni jika menggunakan Windows atau dengan Mac/Linux
#### Apabila menggunakan Windows, aktifkan dengan
```
food-recommender-env\Scripts\activate
```
#### Apabila menggunakan Mac/Linux, aktifkan dengan
```
source food-recommender-env/bin/activate
```

## Install package yang diperlukan dari requirements.txt
```
pip install -r ../requirements.txt
```

## Mengatur .env File
Ubah nama file `.env.temp` menjadi `.env`.
Buka file `.env` dan isikan URL koneksi mongoDB yang sesuai

## Jalankan development server
```
python main.py
```

## Mengakses API
API akan tersedia di `http://localhost:8000` . Request bisa dikirimkan ke endpoint `/predict`

Contoh body request: 
```
{
    "_id" : "648573c85d03c2e375114fc7",
    
    "name": "Joshua Adams",
    
    "spiceLevel": "A little bit spicy",
    
    "likedIngredients": ["beef","pepperoni", "chicken", "tomatoes", "sauce", "peppers", "mushroom"] 
}
```


Contoh return:
```
{

    "uid": "648573c85d03c2e375114fc7",
    
    "recommendation": [
    
        "648573425d03c2e375114fb7",
        "648573435d03c2e375114fba",
        "648573435d03c2e375114fb9",
        "648573445d03c2e375114fc1",
        "648573445d03c2e375114fc0",
        "648573445d03c2e375114fbe"
    ]
}
```
