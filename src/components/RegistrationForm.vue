<template>
    <div class="main-wrapper" :style="{backgroundImage: `url( ${bgImages[this.step-1].url} )` }">
        <b-form>

            <div class="progress-bar-cont">
                <b-container fluid>
                    <b-row align-v="center">
                        <b-col sm="12" md="4">
                            <img class="logo" :src="logo[0].src" alt="" v-if="this.step == 1">
                            <img class="logo" :src="logo[1].src" alt="" v-if="this.step != 1">
                        </b-col>
                        <b-col sm="12" md="8">
                            <div class="progress-cont" v-if="this.step != 1">
                                <p>progress</p>
                                <div class="progress" alt="" >
                                    <div class="progress-bar" :style="{width: progressWidth+'%'}"></div>
                                </div>
                            </div>
                        </b-col>
                    </b-row>
                </b-container>
            </div>

            <section v-if="step == 1" class="form-1">
                <b-container fluid class="form-cont">
                    <b-row align-v="center">
                        <b-col xl="6" class="d-sm-none d-md-block">
                            <!-- do nothing -->
                        </b-col>
                        <b-col xl="6" md="12">   
                            <h1 class="text-center home-main-text">Apply now to work in Dubai</h1>

                            <b-form-row class="form1-wrapper"> 
                                <b-col lg="6" md="12" class="pt-4"> 
                                    <b-form-group>
                                        <b-form-input
                                            v-model="form.fname"
                                            type="text"
                                            placeholder="First name"
                                            required>
                                        </b-form-input>
                                    </b-form-group>
                                </b-col>
                                <b-col lg="6" md="12" class="pt-4"> 
                                    <b-form-group>
                                        <b-form-input
                                            v-model="form.lname"
                                            type="text"
                                            placeholder="Last name"
                                            required>
                                        </b-form-input>
                                    </b-form-group>
                                </b-col>
                                <b-col lg="6" md="12" class="pt-4"> 
                                    <b-form-datepicker v-model="form.dob" ></b-form-datepicker>
                                </b-col>
                                <b-col lg="6" md="12" class="pt-4 gender-cont"> 
                                    <b-form-group v-slot="{ ariaDescribedby }" class="radio-grp">
                                        <b-form-radio v-model="form.gender" :aria-describedby="ariaDescribedby" name="gender" value="male">Male</b-form-radio>
                                        <b-form-radio v-model="form.gender" :aria-describedby="ariaDescribedby" name="gender" value="female">Female</b-form-radio> 
                                        <!--<b-form-checkbox id="checkbox-1" v-model="form.gender" :aria-describedby="ariaDescribedby" name="gender" value="male" unchecked-value="not_accepted"> Male </b-form-checkbox> 
                                        <b-form-checkbox id="checkbox-2" v-model="form.gender" :aria-describedby="ariaDescribedby" name="gender2" value="female" unchecked-value="not_accepted"> Female </b-form-checkbox>-->
                                    </b-form-group>     
                                </b-col>
                                <b-col lg="6" md="12" > 
                                    <b-form-group  class="pt-4">
                                        <b-form-select
                                            v-model="form.residence"
                                            :options="residence"
                                            required >
                                        </b-form-select>
                                    </b-form-group>
                                </b-col>
                                <b-col lg="6" md="12" > 
                                    <b-form-group class="pt-4">
                                        <b-form-select
                                            v-model="form.nationality"
                                            :options="nationality"
                                            required >
                                        </b-form-select>
                                    </b-form-group>
                                </b-col>
                                <b-col lg="6" md="12" class="pt-4"> 
                                    <b-form-group>
                                        <b-form-input
                                            v-model="form.phone"
                                            type="text"
                                            placeholder="Contact Number"
                                            required>
                                        </b-form-input>
                                    </b-form-group>
                                </b-col>
                                <b-col lg="6" md="12" class="pt-4"> 
                                    <b-form-group>
                                        <b-form-input
                                            v-model="form.email"
                                            type="text"
                                            placeholder="Email Address"
                                            required>
                                        </b-form-input>
                                    </b-form-group>
                                </b-col>
                            </b-form-row>
                            
                                                    
                            <b-button class="bttn next float-right mt-5" v-if="step == 1" @click.prevent="nextStep">apply</b-button>
                        </b-col>
                    </b-row>
                </b-container>
            </section>
            <section v-if="step == 2" class="form-2">
                <div class="form-2-wrapper">
                    <div class="btn-cont">
                        <p class="text-title">Have you ever visited Dubai?</p>
                        <p class="btnSec"><BtnOpt /></p>
                    </div>
                    <div class="btn-cont">
                        <p class="text-title">Do you have any friends or family in Dubai?</p>
                        <p class="btnSec"><BtnOpt /></p>
                    </div>
                    <div class="btn-cont">
                        <p class="text-title">How long do you want to stay in Dubai?</p>
                        <p class="btnSec"><BtnOpts /></p>
                    </div>
                </div>
                    <button class="bttn" @click.prevent="backStep">back</button>
                    <button class="bttn next" @click.prevent="nextStep">next</button>
            </section>
            <section v-if="step == 3">
                <div class="qa1">
                    <p class="try">Why do you want to come to Dubai?</p>
                    <p class="btnSec">
                        <CheckB cb_title="Lifestyle" />
                        <CheckB cb_title="Work Opportunities" />
                        <CheckB cb_title="Education" />
                        <CheckB cb_title="Finance" />
                        <CheckB cb_title="Family" />
                        <CheckB cb_title="Business" />
                        <CheckB cb_title="The weather" />
                        <CheckB cb_title="Meeting new people" />
                        <CheckB cb_title="Culture" />

                    </p>
                </div>
                <button class="bttn" @click.prevent="backStep">back</button>
                <button class="bttn next" @click.prevent="nextStep">next</button>
            </section>
            <section v-if="step == 4">
                <button class="bttn" @click.prevent="backStep">back</button>
                <button class="bttn next" @click.prevent="nextStep">next</button>
            </section>
            <section v-if="step == 5">
                <button class="bttn" @click.prevent="backStep">back</button>
                <button class="bttn next" @click.prevent="completedStep">complete application</button>
            </section>

        </b-form>
    </div>
</template>

<script>
import BtnOpt from './BtnOpt.vue';
import BtnOpts from './BtnOpts.vue';
import CheckB from './CheckB.vue';
    export default {
        name: "RegistrationForm",
        components: {
            BtnOpt,
            BtnOpts,
            CheckB
        },
        data: function() {
            return {
                step: 1,

                totalstep: 8,

                progressWidth: null,

                bgImages: [
                    {
                        url: require('@/assets/image/background/form-bg-1.jpg')
                    },
                    {
                        url: require('@/assets/image/background/form-bg-2.jpg')
                    },
                    {
                        url: require('@/assets/image/background/form-bg-3.jpg')
                    },
                    {
                        url: require('@/assets/image/background/form-bg-4.jpg')
                    },
                    {
                        url: ""
                    }
                ],

                logo: [
                    {
                        src: require('@/assets/image/icons/white/white-logo.svg')
                    },
                    {
                        src: require('@/assets/image/icons/black/black-logo.svg')
                    }
                ],

                form: {
                    fname: null,
                    lname: null,
                    gender: null,
                    dob: null,
                    nationality: null,
                    residence: null,
                    phone: null,
                    email: null
                },
                nationality: [{ text: 'Nationality', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
                residence: [{ text: 'Residence', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
                show: true
            };
        },
        methods: {
            nextStep:function() {
                this.step++;
                this.progressWidth += 25;
            },
            backStep:function() {
                this.step--;
                this.progressWidth -= 25;
            },
            completedStep:function() { 
                alert(this.step);
            },
            handleSubmit:function() {
                
            }
        }
    }
</script>

<style>
.qa1{
    margin-top:65px;
}
</style>

