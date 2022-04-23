<!-- Please remove this file from your project -->
 <template>
  <div>
      
                    <h1 class="bg-indigo-100 text-xl"> BALISE B - 5 </h1>

   <!-- This shows a success message if the form was submitted correctly. -->
    <div class="relative rounded-md shadow-sm">
        <form @submit.prevent="createPost">
            <div> <label for="team"> Equipe:  </label>
                <input tye="text" id="team"  placeholder="ton équipe" v-model="formData.team" 
                class="form-input block w-full py-3 px-4 placeholder-gray-500 bg-indigo-100 transition ease-in-out duration-150"/>
            </div>
            <div> <label for="parcours"> Parcours </label>
                <input tye="text" id="parcours" placeholder="ton parcours"  v-model="formData.parcours" 
                class="form-input block w-full py-3 px-4 placeholder-gray-500 bg-indigo-100 transition ease-in-out duration-150"/>
            </div>
             <!-- <div>
            <input type="radio" id="parcours" name="parcours" value="A"
                    checked>
            <label for="A">A</label>
            </div>
             <div>
            <input type="radio" id="parcours" name="parcours" value="B">
            <label for="B">B</label>
            </div> -->
            <!-- <div>
                <label for="parcours">Parcours</label>
                    <select class="form-input block w-full py-3 px-4 placeholder-gray-500 bg-indigo-100 transition ease-in-out duration-150" id="parcours" name="parcours">
                        <option value="A">A</option>
                        <option value="B">B</option>
                    </select>
            </div> -->
            <button class="inline-flex justify-center py-3 px-6 border border-transparent text-base leading-6 font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-500 focus:outline-none focus:border-indigo-700 focus:shadow-outline-indigo active:bg-indigo-700 transition duration-150 ease-in-out mt-3"> Validez la balise</button>
        </form>
     </div>
  </div>
</template>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            formData:{
                team: '',
                parcours: 'B',
                balise: '5'
            }
        }
    },
    methods: {
        createPost(){
            axios.post('https://directus.rubidiumweb.eu/items/co', this.formData)
            .then(response => alert('OK ! Va pour la suivante ! Check la liste'))
            .then(response => console.log(response))
            .catch(error => alert('BUG ! Recommence '));
            setTimeout(() => { window.location.href = "https://larchant2.vercel.app/" ; }, 2000);
            
        }
    }
}
</script>
