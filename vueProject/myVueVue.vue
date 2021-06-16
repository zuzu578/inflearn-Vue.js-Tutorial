<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <title>Document</title>
</head>

<body>
    <div id="root">
        <div>{{first}} X {{second}} result is ? </div>
        <form v-on:submit="onSubmitForm">

            <input type="number" v-model="value">
            <button>answer</button>
            <div>{{value}}</div>
        </form>
        <div id="result">{{result}}</div>
    </div>
    <script>
        const app = new Vue({
            el: '#root',
            data: {
                first: Math.ceil(Math.random() * 9),
                second: Math.ceil(Math.random() * 9),
                value: '',
                result: '',

            },
            methods: {
                onSubmitForm(e) {
                    e.preventDefault();
                    console.log(this);
                    if (this.first * this.second === parseInt(this.value)) {
                        this.result = "correct!";
                        this.first = Math.ceil(Math.random() * 9);
                        this.second = Math.ceil(Math.random() * 9);
                        this.value = '';
                    } else {
                        this.result = "error!";

                        this.value = '';
                    }
                },
            },
        });
    </script>
</body>

</html>