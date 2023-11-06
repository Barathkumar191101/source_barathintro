<template>
  <q-page>
    <div class="q-pa-md q-gutter-sm">
      <q-avatar size="200px" font-size="62px" color="teal" text-color="white">
        <img src="~/assets/image/bkpic.jpg" alt="Avatar Image" class="avatar-img" />
      </q-avatar>
      <h3>Barath Kumar</h3>
      <q-splitter v-model="splitterModel" style="height: 250px">
        <template v-slot:before>
          <q-tabs v-model="tab" vertical class="text-teal">
            <q-tab name="About" icon="person" label="About Myself" />
            <q-tab name="Qualification" icon="book" label="Education">
              <q-btn-group spread dense>
                <q-btn label="SSLC" @click="showSSLC" color="primary" />
                <q-btn label="HSC" @click="showHSC" color="primary" />
                <q-btn label="UG" @click="showUG" color="primary" />
              </q-btn-group>
            </q-tab>
            <q-tab name="hobbies" icon="cricket" label="Interests" />
          </q-tabs>
        </template>
        <template v-slot:after>
          <q-tab-panels v-model="tab" animated swipeable vertical transition-prev="fade" transition-next="fade">
            <q-tab-panel name="About">
              <div class="text-h4 q-mb-md">Myself</div>
              <p>Hi, my name is Barath Kumar S.</p>
              <p>I'm from Madurai</p>
              <p>I have completed my education from Chennai</p>
            </q-tab-panel>
            <q-tab-panel name="Qualification">
              <div class="text-h4 q-mb-md">{{ qualificationDetails }}</div>
            </q-tab-panel>
            <q-tab-panel name="hobbies">
              <div class="text-h4 q-mb-md">Interests</div>
              <p>I enjoy playing outdoor games, particularly Cricket and like to learn new technologies.</p>
              <p>Reading technical magazines, etc.</p>
            </q-tab-panel>
          </q-tab-panels>
        </template>
      </q-splitter>
    </div>
  </q-page>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const tab = ref('About Myself');
    const splitterModel = ref(20);
    const qualificationDetails = ref('');

    const showSSLC = () => {
      qualificationDetails.value =
        'School name: Thanthai Roever Matriculation School, Percentage: 96.5%';
    };

    const showHSC = () => {
      qualificationDetails.value =
        'School name: Sri Ramakrishna Boys Matric Higher Secondary, Percentage: 85%';
    };

    const showUG = () => {
      qualificationDetails.value =
        'College name: SRM, CGPA: 8.99, Branch: Electronics and Communication Engineering';
    };

    return {
      tab,
      splitterModel,
      qualificationDetails,
      showSSLC,
      showHSC,
      showUG,
    };
  },
};
</script>

<style scoped>
/* Add custom styling here */
.q-tab-active {
  background-color: rgb(0, 96, 128);
  /* Customize the active tab background color */
  color: white;
  /* Customize the active tab text color */
}

/* Additional styling for the buttons */
.q-btn-group {
  margin-top: 10px;
}

.q-btn {
  margin-right: 10px;
}
</style>
