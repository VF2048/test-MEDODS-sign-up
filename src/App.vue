<template>
  <div id="app">
    <table>
      <tbody>
        <tr>
          <td><strong class="necessarily">*</strong></td>
          <td>Фамилия</td>
          <td>
            <input
              id="secondn"
              ref="secondn"
              v-on:input="secondname = cheack($event.target.value)"
            />
          </td>
          <td class="fill" v-if="secondname">✔</td>
          <td class="empty" v-else>✖</td>
        </tr>
        <tr>
          <td><strong class="necessarily">*</strong></td>
          <td>Имя</td>
          <td>
            <input v-on:input="name = cheack($event.target.value)" />
          </td>
          <td class="fill" v-if="name">✔</td>
          <td class="empty" v-else>✖</td>
        </tr>
        <tr>
          <td></td>
          <td>Отчество</td>
          <td><input placeholder="" /></td>
        </tr>
        <tr>
          <td><strong class="necessarily">*</strong></td>
          <td>Дата рождения</td>
          <td>
            <input
              class="flex"
              type="date"
              v-on:input="dob = cheack($event.target.value)"
            />
          </td>
          <td class="fill" v-if="dob">✔</td>
          <td class="empty" v-else>✖</td>
        </tr>
        <tr>
          <td></td>
          <td>Номер телефона</td>
          <td>
            <input
              class="flex tel"
              type="number"
              placeholder="8-900-900-1010"
              id="phone"
              name="phone"
              pattern="8-[0-9]{3}-[0-9]{3}-[0-9]{4}"
              required
            />
          </td>
        </tr>
        <tr>
          <td></td>
          <td>Пол</td>
          <td>
            <input
              type="radio"
              id="male"
              value="male"
              name="gender"
              class="check"
            />
            <label for="male">Мужчина</label><br />
            <input
              type="radio"
              id="female"
              value="female"
              name="gender"
              class="check"
            />
            <label for="female">Женщина</label><br />
          </td>
        </tr>
        <tr>
          <td><strong class="necessarily">*</strong></td>
          <td>Группа клиентов</td>
          <td>
            <select
              class="grups"
              multiple
              size="5"
              v-on:input="group = cheack($event.target.value)"
            >
              <option>VIP</option>
              <option>Проблемные</option>
              <option>ОМС</option>
            </select>
          </td>
          <td class="fill" v-if="group">✔</td>
          <td class="empty" v-else>✖</td>
        </tr>
        <tr>
          <td></td>
          <td>Лечащий врач</td>
          <td>
            <select>
              <option>Иванов</option>
              <option>Захаров</option>
              <option>Чернышева</option>
            </select>
          </td>
        </tr>
        <tr>
          <td></td>
          <td>Не отправлять СМС</td>
          <td><input type="checkbox" class="check" /></td>
        </tr>
        <tr>
          <td></td>
          <hr />
          <strong>Адрес</strong>
        </tr>
        <tr>
          <td></td>
          <td>Индекс</td>
          <td>
            <input
              type="namber"
              pattern="[0-9]{6}"
              required
              placeholder="123456"
            />
          </td>
        </tr>
        <tr>
          <td></td>
          <td>Страна</td>
          <td><input type="text" placeholder="Страна" /></td>
        </tr>
        <tr>
          <td></td>
          <td>Область</td>
          <td><input type="text" placeholder="Область" /></td>
        </tr>
        <tr>
          <td><strong class="necessarily">*</strong></td>
          <td>Город</td>
          <td>
            <input
              type="text"
              placeholder="Город"
              v-on:input="city = cheack($event.target.value)"
            />
          </td>
          <td class="fill" v-if="city">✔</td>
          <td class="empty" v-else>✖</td>
        </tr>
        <tr>
          <td></td>
          <td>Улица</td>
          <td><input type="text" placeholder="Улица" /></td>
        </tr>
        <tr>
          <td></td>
          <td>Дом</td>
          <td><input type="namber" required placeholder="Дом" /></td>
        </tr>
        <tr>
          <td></td>
          <td>
            <hr />
            <strong>Документ</strong>
          </td>
        </tr>
        <tr>
          <td><strong class="necessarily">*</strong></td>
          <td>Тип документа</td>
          <td>
            <select v-on:input="doc = cheack($event.target.value)">
              <option value=" ">Выберите документ</option>
              <option>Паспорт</option>
              <option>Свидетельство о рождении</option>
              <option>Вод. удостоверение</option>
            </select>
          </td>
          <td class="fill" v-if="doc">✔</td>
          <td class="empty" v-else>✖</td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td>
            <input
              type="namber"
              pattern="[0-9]{6}"
              required
              placeholder="Серия"
            />
          </td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td>
            <input
              type="namber"
              pattern="[0-9]{6}"
              required
              placeholder="Номер"
            />
          </td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td><input type="text" placeholder="Кем выдан" /></td>
        </tr>
        <tr>
          <td><strong class="necessarily">*</strong></td>
          <td>Дата выдачи</td>
          <td>
            <input
              class="flex"
              type="date"
              v-on:input="dataofissue = cheack($event.target.value)"
            />
          </td>
          <td class="fill" v-if="dataofissue">✔</td>
          <td class="empty" v-else>✖</td>
        </tr>
        <tr>
          <td></td>
          <td>
            <button
              class="enter"
              :disabled="
                !(name && secondname && dob && group && city && dataofissue)
              "
              v-on:click="create = true"
            >
              Создать
            </button>
          </td>
        </tr>
      </tbody>
    </table>
    <div>
      <strong class="necessarily">*</strong>Поле обязательное для заполнения
    </div>
    <dir class="c" v-if="create">
      <dir class="c-box">
        <strong class="c-text">Новый клиент успешно создан!</strong>
      </dir>
    </dir>
  </div>
</template>

<script>
export default {
  name: "App",
  methods: {
    cheack(value) {
      if (value.trim() !== "") return true;
      else return false;
    },
  },
  data() {
    return {
      name: false,
      secondname: false,
      dob: false,
      group: false,
      city: false,
      doc: false,
      dataofissue: false,
      create: false,
      showcheck: false,
    };
  },
};
</script>

<style lang="scss">
$color-shadow: #babecc;
$color-white: #fff;
$color-grey: #ebecf0;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  display: inline-grid;
}
body {
  background-color: $color-grey;
}
div {
  display: flex;
}
td {
  width: 0%;
  padding: 0%;
}
select {
  width: 100%;
}
input,
select {
  box-shadow: inset 2px 2px 5px #babecc, inset -5px -5px 10px $color-white;
  border: 0;
  border-radius: 320px;
  padding: 8px;
  background-color: $color-grey;
  outline: 0;
  &:focus {
    box-shadow: inset 1px 1px 2px $color-shadow,
      inset -1px -1px 2px $color-white;
  }
}
.necessarily {
  color: red;
  font-weight: 900;
}
.name {
  display: flex;
}
.fill {
  color: green;
}
.empty {
  color: red;
}
.enter {
  width: 100%;
  height: 100%;
}
.grups {
  border-radius: 22px;
}
.check {
  box-shadow: 0 0;
  &:focus {
    box-shadow: 0 0;
  }
}
.tel {
  -moz-appearance: textfield;
}
.tel::-webkit-inner-spin-button {
  display: none;
}
.tel::-webkit-outer-spin-button,
.tel::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
.c {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: #7d7777a6;
  margin: 0;
}
.c-box {
  position: absolute;
  margin-top: 100px;
  left: 50px;
}
.c-text {
  font-size: 200%;
}
hr {
  border: none;
  background-color: red;
  color: red;
  height: 2px;
}
.multiselect {
  display: block;
  height: 35px;
}

.selectBox {
  position: relative;
}

.selectBox select {
  width: 100%;
}

.overSelect {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
}

#checkboxes {
  display: block;
  border: 1px #dadada solid;
}

#checkboxes label {
  display: block;
}

#checkboxes label:hover {
  background-color: #1e90ff;
}
</style>
