<template>
  <form @submit.prevent="handleSubmit">
    <label> Email: </label>
    <input type="email" required v-model="email" />

    <label> Password: </label>
    <input type="password" required v-model="password" />

    <label> Role: </label>
    <input type="role" required v-model="role" />

    <label> Skills: </label>
    <input type="text" v-model="tempSkill" @keyup.alt="addSkill" />
    <div v-for="skill in skills" :key="skill" class="pill">
      <span @click="deleteSkill(skill)">{{ skill }}</span>
    </div>

    <select>
      <option value="Developer">Web Developer</option>
      <option value="Designer">Web Designer</option>
    </select>

    <div class="terms">
      <input type="checkbox" v-model="terms" required />
      <label> Accept the terms and conditions</label>
    </div>

    <div class="submit">
      <button>Create an Account</button>
    </div>

    <div>
      <input type="checkbox" value="Shaun" v-model="names" />
      <label>Shaun</label>
    </div>

    <div>
      <input type="checkbox" value="Yoshi" v-model="names" />
      <label>Yoshi</label>
    </div>

    <div>
      <input type="checkbox" value="Mario" v-model="names" />
      <label>Mario</label>
    </div>
  </form>

  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms Accpeted: {{ terms }}</p>
  <p>Terms Accpeted: {{ names }}</p>
</template>

// Probably can remove the v-model stuff because we don't need it 

<script>
export default {
  data() {
    return {
      email: "Mario",
      password: "",
      role: "designer",
      terms: false,
      names: [],
      tempSkill: "",
      skills: [],
    };
  },

  methods: {
    addSkill(e) {
      if (e.key === "," && this.tempSkill) {
        if (!this.skills.includes(this.tempSkill)) {
          this.skills.push(this.tempSkill);
        }
        this.tempSkill = "";
      }
    },
    deleteSkill(skill) {
      this.skills = this.skillsfilter((item) => {
        return skill !== item;
      });
    },
    handleSubmit(){
        console.log('form submitted')
    }
  },
};
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}

label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15 px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}

input,
select {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}

input[type="checkbox"] {
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
  position: relative;
  top: 2px;
}

.pill {
  display: inline-block;
  margin: 20px 10px 0 0;
  padding: 6px 12px;
  background: #eeee;
  border-radius: 20px;
  font-size: 12px;
  letter-spacing: 1px;
  font-weight: bold;
  color: #777;
  cursor: pointer;
}

button {
  background: #0b6dff;
  border: 0;
  padding: 10px 20px;
  margin-top: 20px;
  color: white;
  border-radius: 20px;
}

.submit {
  text-align: center;
}
</style>