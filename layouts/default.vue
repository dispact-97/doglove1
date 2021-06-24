<template>
  <div>
    <nav class="breadcrumb">
        <ul>
            <li><nuxt-link to="/"><i class="fas fa-home"></i>홈으로</nuxt-link></li>
            <li><nuxt-link to="/tripname"><i class="fas fa-info"></i>나라별 수도</nuxt-link></li>
            <li><nuxt-link to="/countryBreeds"><i class="fas fa-suitcase-rolling"></i>국가별 관광지</nuxt-link></li>
        </ul>
</nav>
    <nuxt/>
    <footer class="footer">
       <div class="content has-text-centered">
          <i class="far fa-copysright"></i>2020-2021 모든저작권은 <strong>여행일지</strong>에 있습니다.
         </div>
    </footer>
  </div>
</template>
