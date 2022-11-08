<template>
    <form>
        <label>Email:</label>
        <input type="email" required v-model="email" />
        <label>Password:</label>
        <input type="password" required v-model="password" />
        <label>Role:</label>
        <select v-model="role">
            <option value="Developer">Web developer</option>
            <option value="Designer">Web designer</option>
        </select>
        <label>Skills</label>
        <input type="text" v-model="tempSkill" @keyup="addSkill" />
        <div v-for="skill in skills" :key="skill" class="pill">{{skill}}</div>
        <div class="terms">
            <input type="checkbox" required v-model="terms" /> <label>Accept terms</label>
        </div>
        <div>
            <input type="checkbox" value="Dinand" v-model="names" />
            <label>Dinand</label>
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
    <p>email: {{email}}</p>
    <p>password: {{password}}</p>
    <p>role: {{role}}</p>
    <p>terms: {{terms}}</p>
    <p>names: {{names}}</p>
</template>
<script>
    export default {
        data() {
            return {
                email: '',
                password: '',
                role: 'Designer',
                terms: false, 
                names: [],
                tempSkill: '',
                skills:[]
            }
        },
        methods: {
            addSkill(e) {
                if (e.key === ',' && this.tempSkill) {
                    this.skills.push(this.tempSkill)
                    this.tempSkill = ''

                }
            }
        }
    }
</script>

<style>
    form {
        max-width: 420px;
        margin:0 30px;
        background: white;
        text-align: left;
        padding: 0 40px;
        border-radius: 10px;
    }

    label {
        color: #aaa;
        display: inline-block;
        /*margin: 0 0 15px;*/
        font-size: .6em;
        text-transform: uppercase;
        letter-spacing: 1px;
        font-weight: bold;
    }

    input, select {
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
</style>