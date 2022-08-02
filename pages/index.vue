<!-- 
<template>
    <div>
        <div>
            <div class="flex flex-wrap gap-1 justify-between lg:grid-cols-6 md:grid-cols-4 sm:grid-cols-1">
                <div>
                    <button @click="showSlots" class="inline-block px-6 py-2.5 bg-red-600 text-white font-medium text-xs leading-tight uppercase shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out rounded-full">
                        showSlots
                    </button>
                </div>
                <div class="border-2 border-black w-1/4" v-for="item in timeSlots">
                    <div>
                        <br />
                        <span class="block text-sm font-medium text-slate-700">Start Time-{{ item.startTime }}</span>
                    </div>
                    <br />
                    <div>
                        <br />
                        <span class="block text-sm font-medium text-slate-700">End Time-{{ item.endTime }}</span>
                    </div>
                    <br />
                    <div>
                            <button @click="" type="submit" class="inline-block px-6 py-2.5 bg-blue-600 text-white font-medium text-xs leading-tight uppercase shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out rounded-full">
                                Book Now
                            </button>
                      
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
 import index from '~/pages/form.vue';
export default {
  data() {
    return {
      timeSlots: [],
    };
  },
  methods: {
    showSlots() {
     var d = new Date("2022-08-01 09:00:00");
      var e = new Date("2022-08-01 09:00:00");
      for (let i = 0; i < 20; i++) {
        d.setMinutes(d.getMinutes() + 10);
        e.setMinutes(d.getMinutes() - 10);
        // console.log(d);
        this.timeSlots.push({
          startTime: e.toLocaleTimeString(),
          endTime: d.toLocaleTimeString(),
        });
      }
    },
    book(){
      window.confirm('This Slots is Booked Now');
      document.getElementById("cartBg").style="background-color:green;";
    }
  },
};
</script> -->
