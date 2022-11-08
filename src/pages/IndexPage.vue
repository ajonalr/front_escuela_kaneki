<template>
  <q-layout view="lhr lpR lfr">
    <q-page-container class="bg-light-green window-height window-width row justify-center items-center">
      <div class="column">
        <div class="row">
          <h5 class="text-h5 text-white q-my-md">LOGIN</h5>
        </div>
        <div class="row">

          <q-card class="my-card">
            <div class="text-center">
              <img src="https://cdn-icons-png.flaticon.com/512/295/295128.png" class="q-pa-md" style="width: 50%;">
            </div>
            <q-card-section>

              <q-form class="q-gutter-md">
                <q-input square filled clearable v-model="user.email" type="email" label="email" />
                <q-input square filled clearable v-model="user.password" type="password" label="password" />
                <div class="text-center">

                  <q-btn :loading="loading[0]" color="secondary" @click="save(0)" label="Button" />


                </div>
              </q-form>
            </q-card-section>

          </q-card>

        </div>
      </div>
    </q-page-container>
  </q-layout>

</template>


<script>
import { defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'IndexPage',
  setup() {


    const user = ref({
      email: '',
      password: ''
    })
    const loading = ref([false])
    const progress = ref(false)

    const save = (number) => {
      console.log(user.value.email, user.value.password);

      // we set loading state
      loading.value[number] = true

      // simulate a delay
      setTimeout(() => {
        // we're done, we reset loading state
        loading.value[number] = false
      }, 3000)
    }


    return {
      user,
      save,
      loading,
      progress
    }

  }
})
</script>

