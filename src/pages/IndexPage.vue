<template>
  <q-page class="flex flex-center">
    <q-form @submit="onSubmit" class="q-gutter-md">
      <q-input
        filled
        type="number"
        v-model="age"
        label="hodometro"
        lazy-rules
        :rules="[
          (val) =>
            (val !== null && val !== '') ||
            'Please hodometro em numero inteiro',
        ]"
      />

      <div>
        <q-btn label="Submit" type="submit" color="primary" />
      </div>
    </q-form>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import { useQuasar } from "quasar";
import { ref } from "vue";

export default defineComponent({
  name: "IndexPage",
  setup() {
    const $q = useQuasar();

    const name = ref(null);
    const age = ref(null);
    const accept = ref(false);

    return {
      name,
      age,
      accept,

      onSubmit() {
        $q.notify({
          color: "green-4",
          textColor: "white",
          icon: "cloud_done",
          message: "Submitted",
        });
      },
    };
  },
});
</script>
