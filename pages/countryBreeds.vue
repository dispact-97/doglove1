<template >
    <div>
        <section class="hero is-warning">
            <div class="hero-body">
                <p class="title">
             <i class="fas fa-suitcase-rolling"></i>나라별 관광지
                </p>
                    <p calss="subtitle">
                        나라별 유명한 관광지를 알아보자
                    </p>
            </div>
        </section>
        <hr />
            <section class="columns"></section>
            <div class="columns">
                    <table class="table">
                        <thead>
                            <th>나라이름</th>
                        </thead>
                        <tbody>
                                <template v-for= "pos in tablecountryKeys.length">
                                    <tr :key="pos">
                                        <td>{{pos}}</td>
                                        <td>{{tablecountryKeys[pos -1]}}</td>
                                        <td>
                                            <span class="tag is black" 
                                            v-if= "((tablecountryBreeds[tablecountryBreeds[pos - 1]]), ar.length == 0)">
                                                없음
                                            </span>
                                            <span v-else>
                                                <template v-for= "subbreed in ar">
                                                    <span class="tag is-sucess" :key="subbreed">
                                                    </span>
                                                </template>
                                            </span>
                                        </td>
                                    </tr>
                                </template>

                        </tbody>
                        </table>
                        <div class="content">


            </div>


            <div class="columns"></div>

    </div>
    
</template>

<script>
    import axios from 'axios';
    export default{
       async asyncdData(){
           const countryBreeds = axios.get('https://restcountries.eu/rest/v2/all');
            //alert(Object.keys(countryBreeds));
            return{
                tablecountryBreeds : countryBreeds.data.name,
                tablecountryKeys : Object.Keys(countryBreeds.data.name),
            };
        },
    };
</script>
