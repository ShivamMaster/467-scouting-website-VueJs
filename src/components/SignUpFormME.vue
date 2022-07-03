<template>
  <form>
    <label> Match Number: </label>
    <input type="MatchNumber" required v-model="MatchNumber" />

     <label> Team Number: </label>
    <select>
      <option value="467">467</option>
      <option value="254">254</option>
      <option value="176">176</option>
      <option value="177">177</option>
      <option value="190">190</option>
    </select>

<label> Scouter Name: </label>
    <input type="Scouter Name" required v-model="ScouterName" />
  </form>
</template>

<script>
export default {
  data() {
    return {
      MatchNumber: "",
      TeamNumber: "",
      ScouterName: "",
    };
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

.error {
  color: #ff0062;
  margin-top: 10px;
  font-size: 0.8em;
  font-weight: bold;
}
</style>