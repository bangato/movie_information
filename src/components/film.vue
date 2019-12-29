<template>		
			
	<div class="new"> 
		
		
	<div v-bind="films" v-if="films.Error!='Movie not found!'">

   <div class="column" v-for="film in films.Search" :key="film.Title">
        
    <div class="row">
		
        <div class="col-12 mt-3">     
           
                        
            <div class="card">
                
				
                <div class="card-horizontal" >
                    <div class="img-square-wrapper" >	
                        <img :src="film.Poster" style="width:150px">
                    </div>
                    <div class="card-body" >
                        <h4 class="card-title">{{film.Title}}</h4>
                        <p class="card-text">{{film.Year}}</p>
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

/* Float four columns side by side */
.column {
  float: left;
  width: 25%;
  padding: 0 10px;
}

/* Remove extra left and right margins, due to padding */
.row {margin: 0 -5px;}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Responsive columns */
@media screen and (max-width: 600px) {
  .column {
    width: 100%;
    display: block;
    margin-bottom: 20px;
  }
  }

  .card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  padding: 16px;
  text-align: center;
  background-color: #f1f1f1;
  max-width:500px;
  margin: auto;
  height: 300px;
}

/* ul{

    }
    li{
        list-style-type: none;
        float: left;
        margin: 20px;
    } */
</style>

<!-- <div class="abc">
                <h1 class="subheading grey --text">Team</h1>

	<v-container class="my-5">

        <v-layout row wrap>
            <v-flex xs12 sm6 md4 lg3 v-for="film in films" :key="film[1].Title">
                <v-card flat class="text-xs-center ma-3">
                    <v-responsive class="pt-4">
                         IMAGE GOES HERE
                    </v-responsive>                   
                    <v-card-text>
                        <div class="subheading">{{film[1].Title}}</div>
                        <div class="grey--text">{{film[1].Year}}</div>
                    </v-card-text>
                <v-card-actions>
                    <v-btn flat color="grey">
                        <v-icon small left>message</v-icon>
                        <span></span>
                    </v-btn>
                </v-card-actions>
                </v-card>
            </v-flex>
        </v-layout>
	</v-container>

			</div> -->



            


 <!-- <div class="flex flex-wrap mb-4">
        <div class="xl:w-1/3 lg:w-1/3 md:w-1/3 sm:w-full mb-5 px-4" v-for="movie in films.Search" :key="movie.Title">
            <div class="rounded overflow-hidden shadow-lg">
                <img class="w-full" :src="movie.Poster">
                <div class="px-6 py-4">
                    <div class="font-bold text-xl mb-2">
                        {{ movie.title }}
                        <small class="text-yellow-dark">{{ movie.year}}</small>
                    </div>
                    <small class="text-grey text-base">
                        {{ movie.Type}}
                    </small>
                    <p class="text-grey-darker text-base">
                        {{ movie.overview }}
                    </p>
                </div>
                <div class="px-6 py-4">
                    <span class="inline-block bg-purple-lighter rounded-full px-3 py-1 text-sm font-semibold text-purple-darkest mr-2">Language: {{ movie.original_language }}</span>
                    <span class="inline-block bg-purple-lighter rounded-full px-3 py-1 text-sm font-semibold text-purple-darkest mr-2">Popularity: {{ movie.popularity }}</span>
                </div>
            </div>
        </div>

    </div> -->
