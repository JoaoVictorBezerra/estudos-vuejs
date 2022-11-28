<script>
export default {
    setup() {
        const Order = {
            Title: 'Solicitação',
            Data:
            {
                Making: 'Lorem Ipsum',
                ID: 0,
                Type: 'Lorem Ipsum',
                Status: 'Lorem Ipsum',
                Address: 'Rua Tenente Negrão, 140',
                CardNumber: 123456789,
                Unlock: true,
                UnlockDate: '01/10/2021'
            }
        }
        const User = {
            Title: 'Usuário',
            Data:
            {
                Name: 'Lorem Ipsum',
                SocialName: 'Lorem Ipsum',
                RG: 12345678,
                CPF: 987654321,
                Token: 'Lorem Ipsum'
            }
        }
        const Transaction = {
            Title: 'Transação',
            Data:
            {
                MakingData: 'AAAAAAAAAAA',
                Status: 'BBBBBBBBBBB',
                Value: 'CCCCCCCCCCCC',
                Method: 'DDDDDDDDDDDDD',
                Date: 'EEEEEEEEEEEEEES  '
            }
        }
        return {
            User,
            Order,
            Transaction
        }
    }
}
</script>
<template>
    <div id="container">
        <h1> {{ User.Title }}</h1>
        <ul>
            <li v-for="(value, key) in User.Data" :key="value"> {{ key }} - {{ value }}</li>
        </ul>
    </div>
</template>
<style>
#container ul {
    list-style: none;
}
</style>