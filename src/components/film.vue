

<template>



	<div class="new"> 
		
		
	<div v-bind="films" v-if="films.Error!='Movie not found!'">

				
	<div class="container-fluid" >
    <div class="row">
		
        <div class="col-12 mt-3" }>
			
            <div class="card" style="width:600px">
				
                <div class="card-horizontal">
                    <div class="img-square-wrapper">				
		
                        <img :src="films.Search.Poster" style="width:150px">
                    </div>
                    <div class="card-body" >
                        <h4 class="card-title">{{films.search.Title}}</h4>
                        <p class="card-text">{{films.search.Plot}}</p>
                    </div>
                </div>
                <div class="card-footer">
                    
                </div>
            </div>
        </div>
    </div>
</div>		

	</div>
	<div  v-bind="films" v-if="films.Error=='Movie not found!'">
				<h4>{{films.Error}}</h4>

	</div>

	
	</div>


	

	
</template>



<script>
	export default{
	props:['films']
} 

</script>

<style> 
.new img{
	float:left;
	margin-right:40px;

}
.new h4{
	margin-top:23px;
}

.card-horizontal {
    display: flex;
    flex: 1 1 auto;
}
</style>