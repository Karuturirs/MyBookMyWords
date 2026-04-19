# <center>Vue</center>

Vue bacs js code components

* Data - returns a data objects
* methods - used for event binding or data binding 
* Computed - use with data binding
* Watch -  function name should be name of changing variable 

```vue
const app = Vue.createApp({
  data() {
    return {
      counter: 10,
      name: "",
    };
  },
  methods: {
    submitForm() {
      alert("Submitted!");
    },
    setName(event, lastname) {
      this.name = event.target.value;
    },
    addFn(num) {
      this.counter = this.counter + num;
    },
    reduceFn(num) {
      this.counter = this.counter - num;
    },
    resetInput() {
      this.name = "";
    },
    outputfullName() {
      console.log("Running again...");
      if (this.name === "") {
        return "";
      }
      return this.name + "  " + "Ravi";
    },
  },
  computed: {
    fullName() {
      console.log("Running again...");
      if (this.name === "") {
        return "";
      }
      return this.name + "  " + "Ravi";
    },
  },
  watch: {
    name(value) {
      //reset the value of counter when there is change in name
      this.counter = 0;
    },
  },
});

app.mount("#events");

```

