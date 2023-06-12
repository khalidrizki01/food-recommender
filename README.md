# food-recommender
Back-end untuk menghasilkan rekomendasi berdasarkan karakteristik kegemaran bahan makanan serta tingkat kepedasan pengguna

Inbound port: 8000 (FastAPI)

Route yang tersedia:

'/predict' (POST): menerima data user (terutama field "spiceLevel" dan "likedIngredients") dan mengembalikan uid dan list food_id hasil rekomendasi
