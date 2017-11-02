<template>
  <form @submit.prevent="login" id="my-form"
    class="container"
    action="https://api.staticman.net/v2/entry/QueenYoung/zerostudio/master/"
      method="POST"
    >
    <my-field v-for="(field, index) in fields" :key="index"
      v-bind="field"
      :status="status[index]"
      :index="index"
      @showInput="yo"
    />

    <div class="field">
      <label for="" class="label">同学是女装大佬还是?</label>
      <div class="control">
        <div class="select">
          <select v-model="sex" name="fields[sex]">
            <option disabled value="">性别</option>
            <option value="男">👨🏻</option>
            <option value="女">👩🏻</option>
          </select>
        </div>
      </div>
    </div>


    <div class="field">
      <label for="" class="label">同学哪个院的?</label>
      <div class="control">
        <div class="select">
          <select v-model="college" name="fields[college]">
            <option disabled value="">院系</option>
            <option>软件院</option>
            <option>计信院</option>
            <option>工学院</option>
            <option>其他</option>
          </select>
        </div>
      </div>
    </div>

    <div class="field">
      <label class="label">我们喜欢妹子多的班级🤓</label>
      <div class="control">
        <div class="select">
          <select v-model="classroom" name="fields[classroom]">
            <option disabled value="">班级</option>
            <option v-for="n in 14" :key="n">{{n}}</option>
          </select>
        </div>
      </div>
    </div>

    <div class="field">
      <label class="label">很酷, 真的</label>
      <div class="control">
        <textarea class="textarea" name="fields[introduce]"
        placeholder="介绍一下你自己" v-model="introduce"/>
      </div>
    </div>

    <div class="field">
      <p class="control">
        <button 
          :disabled="!canLogin()"
          class="button is-success"
        >Login</button>
      </p>
    </div>
  </form>
</template>

<script>
import Field from './BaseField'
import Hero from './Hero'

export default {
  components: {
    'my-field': Field,
    hero: Hero
  },
  data() {
    return {
      fields: [
        {
          iconName: 'user',
          placeholder: '比如: 乔布斯',
          type: 'text',
          labelTitle: '名字',
          warning: '不要用英文名耍我',
          name: 'fields[name]'
        },
        {
          iconName: 'mobile',
          placeholder: '不要瞎给手机号码',
          type: 'tel',
          labelTitle: '手机',
          name: 'fields[telphone]'
        }
      ],
      status: Array.apply(null, { length: 2 }),
      inputs: ['', ''],
      sex: '',
      college: '',
      classroom: '',
      introduce: ''
    }
  },
  methods: {
    clearInput() {
      this.inputs = ['', '']
      this.sex = ''
      this.college = ''
      this.classroom = ''
      this.introduce = ''
    },
    yo(input, index) {
      this.inputs.splice(index, 1, input)
      if (index === 0) {
        this.status.splice(index, 1, this.legalName(input))
      } else {
        this.status.splice(index, 1, this.legalTelphone(input))
      }
    },
    login() {
      const fields = {
        fields: [{
          name: this.inputs[0],
          telphone: this.inputs[1],
          classroom: this.classroom,
          sex: this.sex,
          introduce: this.introduce,
          college: this.college
        }]
      }
      const urls = 'https://api.staticman.net/v2/entry/QueenYoung/zerostudio/master/'

      fetch(urls, {
        method: 'POST',
        body: JSON.stringify(fields),
        mode: 'cors',
        headers: {
          'Content-Type': 'application/json'
        }
      })
      this.clearInput()
    },
    canLogin() {
      return (
        this.status.every(Boolean) &&
        [this.sex, this.college, this.classroom, this.introduce].every(Boolean)
      )
    },
    legalTelphone(input) {
      const tel = /^1[3578]\d{9}$/
      return tel.test(input)
    },
    legalName(input) {
      if (input === '乔布斯') {
        alert('老子去你妈的!')
        alert('给我好好填!')
        return false
      }
      const range = [0x4e00, 0x9fa5]
      const codePoints = Array.from(input, code => code.codePointAt(0))
      return codePoints.every(point => point >= range[0] && point <= range[1])
    }
  }
}
</script>



