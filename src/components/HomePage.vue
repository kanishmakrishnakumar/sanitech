<template> 
  <div>
        <v-toolbar color="teal lighten-1" dark max-height="120px">
        <v-spacer />
            <v-toolbar-title class="text-center"> <strong><h1>SANITECH</h1> </strong></v-toolbar-title>
        <v-spacer />
        </v-toolbar>
    <!-- <br>
    <br> -->
    <!-- <br>
    <br>
    <br>  -->
    <v-dialog max-width="900px" min-height="500px" v-model="Start">
        <v-card max-width="900px" min-height="500px" >
            <v-row align="center" justify="center">
                <br>
                <br>
                <!-- <br><br><br><br><br><br><br><br><<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> -->
                <v-col align="center" justify="center">
                    <br>
                    <h1> Your Result </h1>
                    <br>
                   <strong> {{ First }}</strong>
                    <br> <br>
                    <v-icon color="teal lighten-1">mdi-arrow-down-bold</v-icon>  
                    <br> <br>
                   <strong>{{ Second }}</strong>   <br><br>
                    <v-icon color="teal lighten-1">mdi-arrow-down-bold</v-icon>  <br> <br>
                   <strong>{{ Third }}</strong>    <br><br>
                    <v-icon color="teal lighten-1">mdi-arrow-down-bold</v-icon>  <br><br>
                   <strong>{{ Forth }}</strong> <br><br>
                    <!-- First 
                    <v-icon color="teal lighten-1">mdi-arrow-right-bold</v-icon>  
                   Second 
                    <v-icon color="teal lighten-1">mdi-arrow-right-bold</v-icon> 
                    Third 
                    <v-icon color="teal lighten-1">mdi-arrow-right-bold</v-icon> 
                   Forth 
                    {{ First }}
                    <v-icon color="teal lighten-1">mdi-arrow-right-bold</v-icon>  
                    {{ Second }}
                    <v-icon color="teal lighten-1">mdi-arrow-right-bold</v-icon> 
                    {{ Third }}
                    <v-icon color="teal lighten-1">mdi-arrow-right-bold</v-icon> 
                    {{ Forth }} -->
                </v-col>   
            </v-row>
                    
        
    </v-card>
    </v-dialog> 
    <v-card flat>
        <v-card flat color="teal lighten-4">
            <v-img src="sanitation_chain_-_blog_laura_png (1).png">
                
            </v-img>
        </v-card>
        <br><br>
        <v-row>
        <v-col lg="3" cols="4" >
          <v-card
            class="mx-auto"
            max-width="344" color="teal lighten-4"
          >
            
            <v-card-actions>
             <v-menu offset-y v-model="menuOpen1" :close-on-content-click="false">
             <template v-slot:activator="{ on, attrs }">
                <v-col class="text-center">
                <v-btn
                    text
                    color="deep-purple accent-4"
                    v-bind="attrs"
                    v-on="on"
                >
                Onsite Collection
                </v-btn>
            </v-col>
             </template>
             <v-card class="mx-auto" max-width="344">
                <v-card>
                  <v-card-title>
                    Land Requirement &nbsp;  <v-icon color="green">mdi-map-marker-radius</v-icon>
                  </v-card-title>
                 
                  <v-radio-group 
                    class="ml-4"
                    v-model="Onsite.Land"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Ground Water Level &nbsp; <v-icon color="blue"> mdi-waves </v-icon>
                  </v-card-title>
                  
                  <v-radio-group 
                    class="ml-4"
                    v-model="Onsite.Ground"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Deep"
                        value="Deep"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Shallow"
                        value="Shallow"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                     Require Specific Soil Type
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Onsite.Soil"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="No"
                        value="No"
                    ></v-radio>
                    </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                     Vehicular Access &nbsp; <v-icon color="green"> mdi-truck-cargo-container </v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Vehicular"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Yes"
                        value="Yes"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="No"
                        value="No"
                    ></v-radio>
                    </v-radio-group>
                </v-card>
                <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  color="purple"
                  text
                  @click="OnsiteCollection"
                >
                  Apply
                </v-btn>
              </v-card-actions>
             </v-card>
            </v-menu>
             </v-card-actions>
           </v-card>
         </v-col>

         <v-col lg="3" cols="4" >
          <v-card
            class="mx-auto"
            max-width="344" color="teal lighten-4"
          >
        
            <v-card-actions>
                <v-menu offset-y v-model="menuOpen2" :close-on-content-click="false">
             <template v-slot:activator="{ on, attrs }">
                <v-col class="text-center">
                <v-btn
                    text
                    color="deep-purple accent-4"
                    v-bind="attrs"
                    v-on="on"
                >
                PRIMARY TREATMENT OF SLUDGE
                </v-btn>
                </v-col>
             </template>
             <v-card class="mx-auto" max-width="344">
                <v-card>
                  <v-card-title>
                    Land Requirement &nbsp;  <v-icon color="green">mdi-map-marker-radius</v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Primary.Land"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Energy Requirement &nbsp;<v-icon color="red">mdi-lightning-bolt-outline</v-icon>
                  </v-card-title>
                  
                  <v-radio-group 
                    class="ml-4"
                    v-model="Primary.Energy"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Ground Water Level &nbsp; <v-icon color="blue"> mdi-waves </v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Primary.Ground"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Shallow"
                        value="Shallow"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Skill
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Primary.Skill"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Discharge standard 
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Primary.Discharge"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  color="purple"
                  text
                  @click="PrimaryTreat"
                >
                  Apply
                </v-btn>
              </v-card-actions>
             </v-card>
            </v-menu>
             </v-card-actions>
           </v-card>
         </v-col>

         <v-col lg="3" cols="4" >
          <v-card
            class="mx-auto"
            max-width="344" color="teal lighten-4"
          >
            <v-card-actions>
                <v-menu offset-y v-model="menuOpen3" :close-on-content-click="false">
             <template v-slot:activator="{ on, attrs }">
                <v-col class="text-center">
                <v-btn
                    text
                    color="deep-purple accent-4"
                    v-bind="attrs"
                    v-on="on"
                >
                EFFLUENT TREATMENTS
                </v-btn>
                </v-col>
             </template>
             <v-card class="mx-auto" max-width="344">
                <v-card>
                  <v-card-title>
                    Land Requirement &nbsp;  <v-icon color="green">mdi-map-marker-radius</v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Effluent.Land"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Energy Requirement &nbsp;<v-icon color="red">mdi-lightning-bolt-outline</v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Effluent.Energy"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Ground Water Level &nbsp; <v-icon color="blue"> mdi-waves </v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Effluent.Ground"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Shallow"
                        value="Shallow"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Skill
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Effluent.Skill"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Discharge standard
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Effluent.Discharge"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  color="purple"
                  text
                  @click="EffluentTreat"
                >
                  Apply
                </v-btn>
              </v-card-actions>
             </v-card>
            </v-menu>
             </v-card-actions>
           </v-card>
         </v-col>

         <v-col lg="3" cols="4" >
          <v-card
            class="mx-auto"
            max-width="344" color="teal lighten-4"
          >
           
            <v-card-actions>
                <v-menu offset-y v-model="menuOpen4" :close-on-content-click="false">
             <template v-slot:activator="{ on, attrs }">
                <v-col class="text-center">
                <v-btn
                    text
                    color="deep-purple accent-4"
                    v-bind="attrs"
                    v-on="on"
                >
                SLUDGE TREATMENT
                </v-btn>
                </v-col>
             </template>
             <v-card class="mx-auto" max-width="344">
                <v-card>
                  <v-card-title>
                    Land Requirement &nbsp;  <v-icon color="green">mdi-map-marker-radius</v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Sludge.Land"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Energy Requirement &nbsp;<v-icon color="red">mdi-lightning-bolt-outline</v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Sludge.Energy"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Ground Water Level &nbsp; <v-icon color="blue"> mdi-waves </v-icon>
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Sludge.Ground"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Shallow"
                        value="Shallow"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Skill
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Sludge.Skill"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="Low"
                        value="Low"
                    ></v-radio>
                    <v-radio
                        color="purple"
                        label="Medium"
                        value="Medium"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card>
                  <v-card-title>
                    Discharge standard
                  </v-card-title>
                  <v-radio-group 
                    class="ml-4"
                    v-model="Sludge.Discharge"
                    row
                    >
                    <v-radio
                        color="purple"
                        label="High"
                        value="High"
                    ></v-radio>
                </v-radio-group>
                </v-card>
                <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  color="purple"
                  text
                  @click="SludgeTreat"
                >
                  Apply
                </v-btn>
              </v-card-actions>
             </v-card>
            </v-menu>
             </v-card-actions>
           </v-card>
         </v-col>
     </v-row>
     <br>
     <br>
     <v-row>
        <v-col class="text-center">
            <v-btn @click="Start = true" color="teal lighten-5" x-large> Start </v-btn>
        </v-col>
     </v-row>
     
    </v-card>
    
  </div>

</template>

<script>
export default {
    data () {
      return {
        menuOpen1: false,
        menuOpen2: false,
        menuOpen3: false,
        menuOpen4: false,
        Start: false,
        First: '',
        Second: '',
        Third: '',
        Forth: '',
        Vehicular: 'Yes',
        Onsite: {
            Land: 'Low',
            Ground: 'Deep',
            Soil: 'No'
        },
        Primary: {
            Land: 'Low',
            Energy: 'Low',
            Ground: 'Shallow',
            Skill: 'Low',
            Discharge: 'Medium'
        },
        Effluent: {
            Land: 'Low',
            Energy: 'Low',
            Ground: 'Shallow',
            Skill: 'Medium',
            Discharge: 'Medium'
        },
        Sludge: {
            Land: 'Low',
            Energy: 'Low',
            Ground: 'Shallow',
            Skill: 'Low',
            Discharge: 'High'
        }
      }
    },

    methods:{
        OnsiteCollection(){
            this.menuOpen1 = false;
            console.log(this.Onsite.Land);
            console.log(this.Onsite.Ground);
            console.log(this.Onsite.Soil);
            if(this.Onsite.Land === 'Low' && this.Onsite.Ground === 'Deep'){
               this.First = "Twin pit (TP)";
               console.log("..........",this.First);
            }
            else if(this.Onsite.Land === 'Low' && this.Onsite.Ground === 'Shallow'){
                this.First = "Twin pit (TP) && CST && BD";
            }
            else if(this.Onsite.Land === 'Medium' && this.Onsite.Ground === 'Shallow'){
                this.First = "CST";
            }
            else if(this.Onsite.Land === 'Medium' && this.Onsite.Ground === 'Deep'){
                this.First = "Twin pit (TP) && CST && IST";
            }
            else if(this.Onsite.Land === 'High' && this.Onsite.Ground === 'Deep'){
                this.First = " IST";
            }
            else if(this.Onsite.Land === 'High' && this.Onsite.Ground === 'Shallow'){
                this.First = "BD";
            }
            //Primary
           
            //Effluent
           
            //Sludge
           

            
        },
        PrimaryTreat(){
            this.menuOpen2 = false;
            if(this.Primary.Land === 'High' && this.Primary.Energy === 'Low'){
                this.Second = "UDB && PDB";
            }
            else if(this.Primary.Land === 'Low' && this.Primary.Energy === 'Low'){
                this.Second = "Reactor";
            }
            else if(this.Primary.Land === 'Low' && this.Primary.Energy === 'Medium'){
                this.Second = "Settling and thickening tank && ABR";
            }
            else{
                this.Second = "Settling and thickening tank && ABR";
            }
        },
        EffluentTreat(){
            this.menuOpen3 = false;
            if(this.Effluent.Land === 'High' && this.Effluent.Energy === 'High'){
                this.Third = "ASP";
            }
            else if(this.Effluent.Land === 'Low' && this.Effluent.Energy === 'High'){
                this.Third = "SBR";
            }
            else if(this.Effluent.Land === 'Medium' && this.Effluent.Energy === 'High'){
                this.Third = "MBBR";
            }
            else if(this.Effluent.Land === 'Low' && this.Effluent.Energy === 'Medium'){
                this.Third =  "MBR";
            }
            else if(this.Effluent.Land === 'High' && this.Effluent.Energy === 'Low'){
                this.Third = "CW";
            }
            else if(this.Effluent.Land === 'High' && this.Effluent.Energy === 'Medium'){
                this.Third = "ASP && MBR";
            }
            else if(this.Effluent.Land === 'Low' && this.Effluent.Energy === 'Low'){
                this.Third = "MBR && CW";
            }
            else{
                this.Third = "MBBR && CW";
            }
        },
        SludgeTreat(){
            this.menuOpen4 = false;
            if(this.Sludge.Land === 'Medium' && this.Sludge.Energy === 'Low'){
                this.Forth = "Co Composting && Sludge Drying Bed";
            }
            else if(this.Sludge.Land === 'High' && this.Sludge.Energy === 'Low'){
                this.Forth = "Vermicomposting";
            }
            else if(this.Sludge.Land === 'Low' && this.Sludge.Energy === 'Medium'){
                this.Forth = "Filter press && mechanical screw press";
            }
            else if(this.Sludge.Land === 'Low' && this.Sludge.Energy === 'Low'){
                this.Forth = "Co Composting && Vermicomposting && Sludge Drying Bed";
            }
        }
    }
}
</script>
