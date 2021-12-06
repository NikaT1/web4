<template>
  <div>
    <td>
      <label> <input v-bind:name="name" class="defaultBox"
                     type="checkbox"
                     value="-5"
                     checked>
        <p>
          -5
        </p>
      </label>
    </td>
    <td>
      <label>
        <input v-bind:name="name" type="checkbox"
               value="-4">
        <p>
          -4
        </p>
      </label>
    </td>
    <td>
      <label>
        <input v-bind:name="name" type="checkbox"
               value="-3">
        <p>
          -3
        </p>
      </label>
    </td>
    <td>
      <label>
        <input v-bind:name="name" type="checkbox"
               value="-2">
        <p>
          -2
        </p>
      </label>
    </td>
    <td>
      <label>
        <input v-bind:name="name" type="checkbox"
               value="-1">
        <p>
          -1
        </p>
      </label>
    </td>
    <td>
      <label>
        <input v-bind:name="name" type="checkbox"
               value="0">
        <p>
          0
        </p>
      </label>
    </td>
    <td>
      <label>
        <input v-bind:name="name" type="checkbox"
               value="1">
        <p>1
        </p>
      </label>
    </td>
    <td>
      <label>
        <input v-bind:name="name" type="checkbox"
               value="2">
        <p>2
        </p>
      </label>
    </td>
    <td>
      <label>
        <input v-bind:name="name" type="checkbox"
               value="3">
        <p>3
        </p>
      </label>
    </td>
  </div>
</template>

<script>
export default {
  name: "CheckboxRadio",
  props: {
    name: String
  },
  mounted(){
    document.querySelectorAll('input').forEach(x => x.addEventListener("change", (function () {
              if (x.checked) {
                let s = 'input[name=' + this.name + ']';
                let boxes = document.querySelectorAll(s);
                for (let box of boxes) {
                  if (x.value != box.value) {
                    box.checked = false;
                  }
                }
              } else x.checked = true;
            }
        )
        )
    );
  }
}
</script>
