<template>
<main class="flex justify-center">
    <div class="p-2">
        <form @submit="customSubmit" class="bg-blue-100  rounded-lg border-2 px-12 ">
            <table class="grid  content-center">
                <h2 class="text-teal-900  text-center font-bold text-4xl pt-6">Appointment Verification</h2>
                <hr />
                <br />
                <label class="font-bold text-xl" for="firstname">First name:</label>
                <input type="text" v-model="user.firstname" id="firstname" name="firstname" placeholder="Enter your first name" />
                <label class="font-bold text-xl pt-3" for="lastname">Last name:</label>
                <input type="text" v-model="user.lastname" id="lastname" name="lastname" placeholder="Enter your Last name" />
                <label class="font-bold text-xl pt-3" for="email">Email Id: </label>
                <input type="email" v-model="user.email" id="email" name="email" placeholder="Enter your Email id" />
                <label class="font-bold text-xl pt-3" for="number">Phone Number: </label>
                <input type="number" v-model="user.number" id="number" name="number" placeholder="Enter your number" />
                <label class="font-bold text-xl pt-3" for="address"> Address: </label>
                <input type="text" v-model="user.address" id="address" name="address" placeholder="Enter your address" />
                <label class="font-bold text-xl">Purpose of appointment:</label>
                <input type="text" v-model="user.purpose" id="purpose" name="purpose" placeholder="Enter your purpose of appointment" />
                <div class="pt-3">
                    <label class="font-bold text-xl pt-3" for="city"> Select your city: </label>
                    <select v-model="user.city">
                        <option>select</option>
                        <option>Pune</option>
                        <option>Satara</option>
                        <option>Mumbai</option>
                        <option>Nashik</option>
                        <option>Sangli</option>
                        <option>Parbhani</option>
                        <option>other</option>
                    </select>

                </div>
                <div class="pt-3">
                    <label class="font-bold text-xl pt-3">Gender: </label>
                    <label class="" for="male">Male</label>
                    <input type="radio" value="male" v-model="user.gender" name="gender" id="male">
                    <label class="" for="female">Female</label>
                    <input type="radio" value="female" v-model="user.gender" name="gender" id="female">
                </div>
                <div class="pt-3">
                    <label class="font-bold text-xl pt-3" for="time"> Selected Time Slot: </label>
                    <select v-model="user.time">
                        <option>select</option>
                        <option>10:00 To 10:10</option>
                        <option>10:20 To 10:30</option>
                        <option>10:40 To 10:50</option>
                        <option>11:00 To 11:10</option>
                        <option>11:20 to 11:30 </option>
                        <option>11:20 to 11:30</option>
                        <option>11:20 to 11:30</option>
                        <option>11:40 to 11:50</option>
                        <option>12:00 To 12:10</option>
                        <option>12:20 To 12:30</option>
                        <option>12:40 to 12:50</option>
                        <option>01:10 to 01:20</option>
                        <option>01:30 to 01:40</option>
                        <option>02:20 to 02:30</option>
                        <option>03:20 to 03:30</option>

                    </select>

                </div>
                <!-- <div class="pt-3"> -->

                <!-- </div> -->
                <div class="text-center pt-10">
                    <button class="py-2 px-10 mr-5 bg-blue-500 hover:bg-blue-700 text-white font-bold text-center rounded-md mb-3" type="submit" @click="customSubmit">Book </button>
                    <button class="py-2 px-10 bg-blue-500 hover:bg-blue-700 text-white font-bold text-center rounded-md mb-3" type="reset"> Cancel </button>
                </div>
            </table>
        </form>
        <br>
        <table class="list">
            <h1 class="text-teal-900 text-xl font-bold pt-1">DataBase table:</h1>
            <tr>
                <th class="px-4 border-black rounded-lg border-2">Id</th>
                <th class="px-4 border-black rounded-lg border-2">First Name</th>
                <th class="px-4 border-black rounded-lg border-2">Last Name</th>
                <th class="px-4 border-black rounded-lg border-2">Email Id</th>
                <th class="px-4 border-black rounded-lg border-2">Number</th>
                <th class="px-4 border-black rounded-lg border-2">Address</th>
                <th class="px-4 border-black rounded-lg border-2">City</th>
                <th class="px-4 border-black rounded-lg border-2">Gender</th>
                <th class="px-4 border-black rounded-lg border-2">selected time</th>
                <th class="px-4 border-black rounded-lg border-2">purpose of the appointment:</th>
                 <th class="px-4 border-black rounded-lg border-2">Action</th>
            </tr>
            <tr v-for="(item, i) in myarr" :key="item">
                <td class="px-4 border-black rounded-lg border-2">{{item.id = i+1}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.firstname}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.lastname}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.email}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.number}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.address}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.city}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.gender}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.time}}</td>
                <td class="px-4 border-black rounded-lg border-2">{{item.purpose}}</td>
                 <td class="px-4 border-black rounded-lg border-2"> <button class="py-1 px-5 bg-green-500 hover:bg-green-700 text-white font-bold text-center rounded-md" > Booked </button></td>
            </tr>
        </table>
    </div>
</main>
</template>

<script>
//import { isThisExpression } from '@babel/types';
export default {
    data() {
        return {
            isEdit: false,
            indexEdit: -1,
            myarr: [],
            user: {
                id: 0,
                firstname: '',
                lastname: '',
                email: '',
                number: '',
                address: '',
                city: '',
                gender: '',
                time: '',
                purpose: '',
            },
        };
    },
    methods: {
        customSubmit(event) {
            event.preventDefault();
            if (this.isEdit == true) {
                this.myarr[this.indexEdit] = this.user;
                this.isEdit = false;
                this.indexEdit = -1;
            } else {
                this.myarr.push(this.user);
            }
            this.user = {
                id: 0,
                firstname: '',
                lastname: '',
                email: '',
                number: '',
                address: '',
                city: '',
                gender: '',
                time: '',
                purpose: '',
            };
        },
        customDelete(index) {
            this.myarr.splice(index, 1);
        },
        customEdit(index) {
            this.user.firstname = this.myarr[index].firstname;
            this.user.lastname = this.myarr[index].lastname;
            this.user.email = this.myarr[index].email;
            this.user.number = this.myarr[index].number;
            this.user.address = this.myarr[index].address;
            this.user.city = this.myarr[index].city;
            this.user.gender = this.myarr[index].gender;
            this.user.profession = this.myarr[index].time;
            this.user.profession = this.myarr[index].profession;

            this.isEdit = true;
            this.indexEdit = index;
        }
    }
}
</script>
