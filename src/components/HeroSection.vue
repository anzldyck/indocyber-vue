<template>
  <section class="container">
    <img src="https://api.elements.buildwithangga.com/storage/files/2/assets/Header/Header-House/bg-header.svg"
        alt="bg-header" class="img-header d-none d-md-block">
    <div class="row mx-0" id="header" style="text-align: left">
        <div class="col-xl-6">
            <div class="title">
                <h1>
                    Find your Favorite books
                </h1>
            </div>
            <div class="d-flex stat">
                <div class="text-left me-4 me-md-5">
                    <h2>
                        37
                    </h2>
                    <p>
                        Komik
                    </p>
                </div>
                <div class="vr"></div>
                <div class="px-md-5 px-4">
                    <h2>
                        80
                    </h2>
                    <p>
                        Sains
                    </p>
                </div>
                <div class="vr"></div>
                <div class="ms-4 ms-md-5">
                    <h2>
                        760
                    </h2>
                    <p>
                        Programming
                    </p>
                </div>
            </div>
            <div class="stat">
                <p class="descript-head">
                    The more that you read, the more things you will know. The more that you learn, the more places you’ll go
                </p>
            </div>
            <div>
                <button class="btn btn-blue px-5 py-3 shadow">
                    Find Books
                </button>
            </div>
        </div>
        <div class="col-xl-6 my-auto">
            <div class="gallery row p-md-4 section scrolling-wrapper flex-row flex-nowrap">
                <!-- CARD 1 -->
                 <div class="card-hotel-carousel">
                            <div class="image-placeholder">
                                <img src="https://i.pinimg.com/474x/67/de/12/67de123d80c51f8bfb29934648624f99.jpg"
                                    alt="images" />
                            </div>
                            <div class="card-details">
                                <div class="caption">Marshland</div>
                                <span class="sub-caption">Mathew Olshan</span>
                            </div>
                            <div class="bottom-text d-flex flex-row justify-content-between">
                                <div class="price-content flex-grow-1">
                                    <span>Start from</span> <span class="price">40 USD</span>
                                </div>
                                <div class="rating d-flex align-items-center">
                                    <img src="https://api.elements.buildwithangga.com/storage/files/2/assets/Header/Header-House/star-yellow.svg"
                                        alt="star" />
                                    <span>4.8</span>
                                </div>
                            </div>
                </div>
                <!-- END CARD 1 -->
                <!-- CARD 2 -->
                <div class="card-hotel-carousel">
                            <div class="image-placeholder">
                                <img src="https://i.pinimg.com/474x/14/75/39/147539aac2b751e5d0813c346ac4be43.jpg"
                                    alt="images" />
                            </div>
                            <div class="card-details">
                                <div class="caption">The Throught Breaking</div>
                                <span class="sub-caption">Cate Emond</span>
                            </div>
                            <div class="bottom-text d-flex flex-row justify-content-between">
                                <div class="price-content flex-grow-1">
                                    <span>Start from</span> <span class="price">40 USD</span>
                                </div>
                                <div class="rating d-flex align-items-center">
                                    <img src="https://api.elements.buildwithangga.com/storage/files/2/assets/Header/Header-House/star-yellow.svg"
                                        alt="star" />
                                    <span>4.8</span>
                                </div>
                            </div>
                        </div>
                <!-- END CARD 2 -->
                <!-- CARD 3 -->
                <div class="card-hotel-carousel">
                            <div class="image-placeholder">
                                <img src="https://i.pinimg.com/474x/66/ab/e4/66abe4b5abbd209f4a09fcd8afc207d9.jpg"
                                    alt="images" />
                            </div>
                            <div class="card-details">
                                <div class="caption">The Jungle Book</div>
                                <span class="sub-caption">Rudyard</span>
                            </div>
                            <div class="bottom-text d-flex flex-row justify-content-between">
                                <div class="price-content flex-grow-1">
                                    <span>Start from</span> <span class="price">40 USD</span>
                                </div>
                                <div class="rating d-flex align-items-center">
                                    <img src="https://api.elements.buildwithangga.com/storage/files/2/assets/Header/Header-House/star-yellow.svg"
                                        alt="star" />
                                    <span>4.8</span>
                                </div>
                            </div>
                        </div>
                <!-- END CARD 3 -->
            </div>
        </div>
    </div>
    <div class="container">
        <div class="row content">
            <div class="col-12 px-md-0 my-auto">
                <div class="tagline">
                    RECOMENDATION
                </div>
                <div class="gallery row p-md-4 section scrolling-wrapper flex-row flex-nowrap" v-if="this.books.length > 0">
                    <div class="card-hotel-carousel" v-for="itemBooks in books" :key="itemBooks.id">
                        <div class="image-placeholder">
                            <img :src="itemBooks.photo"
                                alt="images" />
                        </div>
                        <div class="card-details">
                            <div class="caption">{{ itemBooks.title }}</div>
                            <span class="sub-caption">Stok : {{ itemBooks.stocks }}</span>
                        </div>
                        <div class="bottom-text d-flex flex-row justify-content-between">
                            <div class="price-content flex-grow-1">
                                <span>Start from</span> <span class="price">40 USD</span>
                            </div>
                            <div class="rating d-flex align-items-center">
                                <img src="https://api.elements.buildwithangga.com/storage/files/2/assets/Header/Header-House/star-yellow.svg"
                                    alt="star" />
                                <span>4.8</span>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-lg-12" v-else>
                    <p>Data tidak ditemukan</p>
                </div>
            </div>
        </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
    name: 'HeroSection',
    data() {
        return {
            books: []
        }
    },
    mounted() {
        axios
        .get("http://127.0.0.1:8000/api/books")
        .then(res => (this.books = res.data.data))
        .catch(err => console.log(err));
    }
}
</script>

<style scoped>
body #header {
    margin-top: 138px;
    margin-bottom: 100px;
    width: 100% !important;
}

@media screen and (max-width: 768px) {
    body #header {
        margin-top: 50px;
        margin-bottom: 50px;
    }
}

body .content .content .tagline {
    font-family: Poppins;
    font-style: normal;
    font-weight: bold;
    font-size: 18px;
    line-height: 27px;
    /* identical to box height */
    color: #DB0D70;
}

body .img-header {
    z-index: -1;
    position: absolute;
    top: 0;
    right: 0;
}

body .explore {
    background-color: #080E09;
    padding-top: 100px;
    padding-bottom: 50px;
}

@media screen and (max-width: 768px) {
    body .explore {
        padding-top: 50px;
        padding-bottom: 50px;
    }
}

body .explore .descript-explore {
    max-width: 75%;
}

body .pt-35 {
    padding-top: 35px;
}

body .title h1 {
    font-size: 72px;
    font-weight: 700;
    line-height: 150%;
}

@media screen and (max-width: 768px) {
    body .title h1 {
        font-size: 48px;
    }
}

body .stat {
    margin-top: 48px;
}

body .stat h2 {
    font-size: 48px;
    font-weight: 800;
}

@media screen and (max-width: 768px) {
    body .stat h2 {
        font-size: 28px;
    }
}

body .stat p {
    font-size: 16px;
    color: #ADB2B8;
    font-weight: 400;
    line-height: 28px;
}

body .stat .descript-head {
    max-width: 90%;
}

body .btn-blue {
    background-color: #0F52BA;
    color: white;
    font-weight: 600;
    font-size: 16px;
    border-radius: 12px;
    margin-top: 48px;
}

body .gallery {
    padding: 10px 0;
}

@media only screen and (max-width: 768px) {
    body .gallery {
        margin: 50px 0;
    }
}

body .gallery .card-hotel-carousel {
    width: 325px;
    margin-right: 64px;
    padding: 28px 28px 40px;
    border-radius: 28px;
    background: white;
    -webkit-box-shadow: 20px 8px 18px rgba(178, 177, 255, 0.05);
    box-shadow: 20px 8px 18px rgba(178, 177, 255, 0.05);
}

@media only screen and (max-width: 768px) {
    body .gallery .card-hotel-carousel {
        margin-right: 20px;
    }
}

body .gallery .card-hotel-carousel .image-placeholder {
    width: 268px;
    height: 190px;
}

body .gallery .card-hotel-carousel .image-placeholder img {
    width: 100%;
    height: 100%;
    -o-object-fit: cover;
    object-fit: cover;
    border-radius: 16px;
}

body .gallery .card-hotel-carousel .card-details {
    padding-bottom: 53px;
    height: 150px;
}

body .gallery .card-hotel-carousel .card-details .caption {
    font-weight: 700;
    font-size: 24px;
    color: #080E09;
    margin-top: 24px;
}

body .gallery .card-hotel-carousel .card-details .sub-caption {
    font-weight: 400;
    color: #ADB2B8;
}

body .gallery .card-hotel-carousel .bottom-text .price-content {
    color: #080E09;
    font-size: 16px;
}

body .gallery .card-hotel-carousel .bottom-text .price-content span {
    font-weight: 400;
}

body .gallery .card-hotel-carousel .bottom-text .price-content span.price {
    font-weight: 700;
}

body .gallery .card-hotel-carousel .bottom-text .rating {
    font-weight: 700;
    font-size: 16px;
    color: #FF9900;
}

body .gallery .card-hotel-carousel .bottom-text .rating img {
    margin-top: -1px;
    margin-right: 5px;
}

@media screen and (min-width: 600px) {
    body .image-content .img-fluid {
        height: 144.953px;
    }
}

body .text-content h1 {
    font-size: 60px !important;
    line-height: 150%;
    color: white;
}

body .text-content p {
    font-size: 16px;
    color: #ADB2B8;
    font-weight: 400;
    line-height: 28px;
    padding-bottom: 108px;
}

body .place .img-place-header {
    width: 100% !important;
}

body .scrolling-wrapper {
    overflow-x: auto;
}

body .section::-webkit-scrollbar {
    height: 0 !important;
}

body .section::-webkit-scrollbar-track {
    background-color: #e4e4e4;
    border-radius: 100px;
}

body .section::-webkit-scrollbar-thumb {
    background-color: #05BB2D;
    border-radius: 100px;
}
</style>