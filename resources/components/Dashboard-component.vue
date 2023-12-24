<style scoped>
    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
        /* display: none; <- Crashes Chrome on hover */
        -webkit-appearance: none;
        margin: 0; /* <-- Apparently some margin are still there even though it's hidden */
    }

    input[type=number] {
        -moz-appearance:textfield; /* Firefox */
    }

    .inputNumber{
        /* border: 0; */
        text-align: right;
    }

    .table-one tr th{
        background-color: yellow;
    }

    .table-two thead tr th {
        background-color: rgb(182, 179, 179);
    }
</style>

<template>

    <div class="m-5">
        <table class="table-one table table-bordered">
            <thead class="text-center">
                <tr>
                    <th>รหัสผู้จำหน่าย</th>
                    <th>เดือน</th>
                    <th>เป้าการขายของฟอร์ด</th>
                    <th>แผนการขายของผู้จำหน่าย</th>
                    <th>% บรรลุเป้าการขาย</th>
                </tr>
            </thead>
            <tbody class="text-center">
                <tr>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                </tr>
            </tbody>
        </table>

        <table class="table-two table table-bordered mt-5">
            <thead class="text-center">
                <tr>
                    <th>รุ่นรถ</th>
                    <th>เป้าการขายรายรุ่น</th>
                    <th>% ยอดจองที่กลายเป็นยอดส่งมอบ</th>
                    <th>ยอดจองทั้งหมดที่ต้องการ</th>
                    <th>ประมาณการยอดจองคงค้าง</th>
                    <th>ยอดจองใหม่ที่ต้องการ</th>
                    <th>คาดการณ์ยอดจองที่จะได้รับ</th>
                    <th>+ เพียงพอ <br> - ไม่เพียงพอ</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, index) in carList">
                    <td style="text-align: left;">{{ item }}</td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                    <td><input class="inputNumber" type="number"></td>
                </tr>
                <tr class="text-center">
                    <td>รวม</td>
                    <td>0</td>
                    <td>0</td>
                    <td></td>
                    <td>0</td>
                    <td>0</td>
                    <td></td>
                    <td>0</td>
                </tr>
            </tbody>
        </table>
    </div>
  
</template>

<script>
    export default {
        data() {
            return {
                carList : [
                    "Everest",
                    "Raptor 3.0 Benzine",
                    "Raptor 2.0 Diesel",
                    "Stormtrak",
                    "Wildtrak",
                    "DBL XLT / Sport",
                    "RAS XLS / DBL XLS",
                    "RAS XL+",
                    "อื่นๆ",
                ]
            }
        },
    }

</script>