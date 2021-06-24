<template>
	<div>
		<section class="hero is-warning">
			<div class="hero-body">
				<p class="title">
                    <i class="fas fa-suitcase-rolling"></i> 국가별 관광지</p>
				<p class="subtile">
					국가별 관광지를 알아보자
				</p>
			</div>
		</section>
		<hr />
		<section class="columns"></section>
		<div class="column">
			<table class="table">
				<thead>
					<th>번호</th>
					<th>국가 이름</th>
				</thead>
				<tbody>
					<template v-for="pos in tablecountryKeys.length">
						<tr :key="pos">
							<td>{{ pos }}</td>
							<td>{{ tablecountryKeys[pos - 1] }}</td>
							<td>
								<span class="tag is-black"
									v-if="
((ar = tableCountrybreeds[tablecountryKeys[pos - 1]]),ar.length == 0)">
                                    없음
                                    </span>
								<span v-else>
                                    <template v-for="subbreed in ar">
                                        <span class="tag is-success" :key="subbreed">
                                            {{
											subbreed
										    }}
                                        </span>
                                        &nbsp;</template>
								</span>
							</td>
						</tr>
					</template>
				</tbody>
			</table>
			<div class="content">
				<p class="tag is-danger">출처</p>
				<a href="https://restcountries.eu/#api-endpoints-all">Rest Countries</a><br />
				<a
					class="button is-primary is-small"
					href="https://restcountries.eu/rest/v2/all"
					>List all breeds</a
				>
			</div>
		</div>
		<div class="column"></div>
	</div>
</template>
<script>
	import axios from 'axios';
	export default {
		async asyncData() {
			const countryBreeds = await axios.get('https://restcountries.eu/rest/v2/alpha/col');
			//alert(Object.keys(countryBreeds));
			return {
				tableCountrybreeds: countryBreeds.data.name,
				tablecountryKeys: Object.keys(countryBreeds.data.name),
			};
		},
	};
</script>