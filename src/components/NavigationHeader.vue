<template>
  <nav class="navbar navbar-expand-lg navbar-light pt-3 pt-lg-5">
        <div class="container">
            <a class="navbar-brand" href="#">
                <h5 class="mb-0">Books</h5>
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent"
                aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse text-center" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item active">
                        <a class="nav-link active border-bottom" aria-current="page" href="#">Home</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name: 'NavigationHeader',
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap");

* {
    font-family: 'Inter', sans-serif !important;
}

body {
    background-color: #FFFFFF;
}

body nav .navbar-brand h5 {
    font-weight: 700 !important;
    size: 28px;
    line-height: 150%;
}

body nav .navbar-nav .nav-link {
    font-size: 16px;
    font-weight: 600;
    color: #739AD4 !important;
    margin: 0 30px;
}

body nav .navbar-nav .active {
    color: #080E09 !important;
    width: 100%;
    display: -webkit-box !important;
    display: -ms-flexbox !important;
    display: flex !important;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
}

body nav .navbar-nav .active a {
    width: 12px;
}

body nav .navbar-nav .border-bottom {
    border-bottom: 2px solid #0F52BA !important;
}

@media screen and (min-width: 993px) {
    body nav .navbar-nav {
        margin-left: 560px;
    }
}
</style>