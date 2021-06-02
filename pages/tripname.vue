<template>
    <div>
        <section class="hero is-link">
            <div class="hero-body">
                <p class="title">
             <i class="fas fa-flag"></i>나라별 수도를 알아보자
                </p>
            </div>
        </section>

        <section class="columns">
            <div class="column">
                <table class="table is-hoverable is-fullwidth">
                    <thead>
                        <tr>
                            <th>나라 이름</th>
                            <th>수도 이름</th>
                        </tr>
                    </thead>

                    <tbody>
                   <template v-for="pos in table_country_name.length">
                            <tr :key="pos">
                                 <td>{{ table_country_name[pos - 1].name }}</td>
                            </tr>
                        </template>
                        </tbody>

                </table>

            </div>
        </section>
    </div>
    
</template>

<script>
import countryname from "~/assets/countryname.json";
export default{
    data(){
        return
        {
            table_country_name: countryname.name
        };
    }
};
</script>
