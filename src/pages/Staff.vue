<template>
<section class="staff">
  <div class="staff__items">
    <div class="staff__header">
      <h2 class="staff__title">Сотрудники</h2>
      <div class="staff__company">
        <img :src="company.img" alt="логотип компании">
        <div class="staff__company-title">{{company.name}}</div>
      </div>
    </div>
    <div class="staff__btns">
      <div class="staff__btns-item">
        <button class="staff__btn btn1">
          <svg xmlns="http://www.w3.org/2000/svg" width="22" height="14" viewBox="0 0 22 14" fill="none">
            <path d="M7 1.6625C8.015 1.6625 8.8375 2.485 8.8375 3.5C8.8375 4.515 8.015 5.3375 7 5.3375C5.985 5.3375 5.1625 4.515 5.1625 3.5C5.1625 2.485 5.985 1.6625 7 1.6625ZM7 9.5375C9.59875 9.5375 12.3375 10.815 12.3375 11.375V12.3375H1.6625V11.375C1.6625 10.815 4.40125 9.5375 7 9.5375ZM7 0C5.06625 0 3.5 1.56625 3.5 3.5C3.5 5.43375 5.06625 7 7 7C8.93375 7 10.5 5.43375 10.5 3.5C10.5 1.56625 8.93375 0 7 0ZM7 7.875C4.66375 7.875 0 9.0475 0 11.375V14H14V11.375C14 9.0475 9.33625 7.875 7 7.875Z" fill="white"/>
            <path d="M19.75 2.25V0H18.25V2.25H16V3.75H18.25V6H19.75V3.75H22V2.25H19.75Z" fill="white"/>
          </svg>
          <span v-if="!isMob">Добавить сотрудника</span>
        </button>
        <button class="staff__btn btn2">
          <svg xmlns="http://www.w3.org/2000/svg" width="15" height="14" viewBox="0 0 15 14" fill="none">
            <path d="M7.5 12.6C4.413 12.6 1.9 10.087 1.9 7C1.9 3.913 4.413 1.4 7.5 1.4C10.587 1.4 13.1 3.913 13.1 7C13.1 10.087 10.587 12.6 7.5 12.6ZM7.5 0C6.58075 0 5.67049 0.18106 4.82122 0.532843C3.97194 0.884626 3.20026 1.40024 2.55025 2.05025C1.2375 3.36301 0.5 5.14348 0.5 7C0.5 8.85651 1.2375 10.637 2.55025 11.9497C3.20026 12.5998 3.97194 13.1154 4.82122 13.4672C5.67049 13.8189 6.58075 14 7.5 14C9.35651 14 11.137 13.2625 12.4497 11.9497C13.7625 10.637 14.5 8.85651 14.5 7C14.5 6.08075 14.3189 5.17049 13.9672 4.32122C13.6154 3.47194 13.0998 2.70026 12.4497 2.05025C11.7997 1.40024 11.0281 0.884626 10.1788 0.532843C9.3295 0.18106 8.41925 0 7.5 0ZM8.2 3.5H6.8V6.3H4V7.7H6.8V10.5H8.2V7.7H11V6.3H8.2V3.5Z" fill="#E31243"/>
          </svg>
          <span v-if="!isMob">Создать новый отдел</span>
        </button>
      </div>
      <div class="staff__btns-item">
        <button class="staff__btn btn3">
          <svg v-if="isMob" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path fill="#fff" d="M5,20H19V18H5M19,9H15V3H9V9H5L12,16L19,9Z"/></svg>
          <span v-else>Скачать список прошедших</span>
        </button>
        <button class="staff__btn btn4">
          <svg v-if="isMob" xmlns="http://www.w3.org/2000/svg" width="17" height="17" viewBox="0 0 24 24"><path fill="#fff" d="M23,12L19,8V11H10V13H19V16M1,18V6C1,4.89 1.9,4 3,4H15A2,2 0 0,1 17,6V9H15V6H3V18H15V15H17V18A2,2 0 0,1 15,20H3A2,2 0 0,1 1,18Z"/></svg>
          <span v-else>Экспорт</span>
        </button>
        <button class="staff__btn btn3">
          <svg v-if="isMob" xmlns="http://www.w3.org/2000/svg" width="10" height="12" viewBox="0 0 10 12" fill="none">
            <path d="M2.88237 9.17647V4.94118H0.0588379L5.00001 0L9.94119 4.94118H7.11766V9.17647H2.88237ZM0.0588379 12V10.5882H9.94119V12H0.0588379Z" fill="white"/>
          </svg>
          <span v-else>Загрузить списком</span>
        </button>
      </div>
    </div>
    <div class="staff__search">
      <input placeholder="Поиск по ФИО" v-model="search">
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16" fill="none">
        <path d="M5.94286 0C7.519 0 9.03059 0.62612 10.1451 1.74062C11.2596 2.85512 11.8857 4.36671 11.8857 5.94286C11.8857 7.41486 11.3463 8.768 10.4594 9.81029L10.7063 10.0571H11.4286L16 14.6286L14.6286 16L10.0571 11.4286V10.7063L9.81029 10.4594C8.768 11.3463 7.41486 11.8857 5.94286 11.8857C4.36671 11.8857 2.85512 11.2596 1.74062 10.1451C0.62612 9.03059 0 7.519 0 5.94286C0 4.36671 0.62612 2.85512 1.74062 1.74062C2.85512 0.62612 4.36671 0 5.94286 0ZM5.94286 1.82857C3.65714 1.82857 1.82857 3.65714 1.82857 5.94286C1.82857 8.22857 3.65714 10.0571 5.94286 10.0571C8.22857 10.0571 10.0571 8.22857 10.0571 5.94286C10.0571 3.65714 8.22857 1.82857 5.94286 1.82857Z" fill="#128BE3"/>
      </svg>
    </div>
  </div>
  <div class="staff__lists">
    <div class="staff__lists-info">Показаны записи 1-113 из 113.</div>
    <div class="staff__list list-header">
      <MyCheckbox v-model="allCheckbox" :name="'all'"/>
      <div class="staff__list-title fio">ФИО</div>
      <div class="staff__list-title position">Должность</div>
      <div class="staff__list-title status">Статус МО</div>
      <div class="staff__list-title recording-date">Дата записи</div>
      <div class="staff__list-title pass-date">Дата прохож<br>дения</div>
    </div>

    <div class="staff__list-item" v-for="dep in getDepFilter" :key="dep.id">
      <div class="staff__list list-departments" @click="setOpen(dep)">
        <div class="staff__list-departments">{{dep.name}}<span>{{dep.staff.length}}</span></div>
        <div class="staff__list-departments-btn">
          <button class="staff__list-btn">
            <svg width="12" height="12" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M11.805 2.69463C12.065 2.43466 12.065 2.00139 11.805 1.75476L10.2452 0.194973C9.99861 -0.064991 9.56534 -0.064991 9.30537 0.194973L8.07888 1.4148L10.5785 3.91446L11.805 2.69463ZM0 9.50035V12H2.49965L9.87196 4.62103L7.37231 2.12137L0 9.50035Z" fill="#E31243"/>
            </svg>
          </button>
          <button class="staff__list-btn">
            <svg width="11" height="14" viewBox="0 0 11 14" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M10.8889 0.777778H8.16667L7.38889 0H3.5L2.72222 0.777778H0V2.33333H10.8889V0.777778ZM0.777778 12.4444C0.777778 12.857 0.941666 13.2527 1.23339 13.5444C1.52511 13.8361 1.92077 14 2.33333 14H8.55556C8.96811 14 9.36378 13.8361 9.6555 13.5444C9.94722 13.2527 10.1111 12.857 10.1111 12.4444V3.5H0.777778V12.4444Z" fill="#E31243"/>
            </svg>
          </button>
          <button class="staff__list-btn svg-rotate" :class="{'svg--rotate': dep.isOpen}">
            <svg width="10" height="6" viewBox="0 0 10 6" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M1.175 6L5 2.2915L8.825 6L10 4.8583L5 0L0 4.8583L1.175 6Z" fill="#128BE3"/>
            </svg>
          </button>
        </div>
      </div>
      <ul class="staff__list-dropdown" v-if="dep.isOpen">
        <li class="staff__list-people" v-for="list in dep.staff" :key="list.id">
          <div style="display: flex">
            <MyCheckbox v-model="list.isCheck" :name="`${dep.code+list.id}`"/>
            <div class="staff__list-li fio">{{list.fio}}</div>
            <div class="staff__list-li position">{{list.position}}</div>
            <div class="staff__list-li status"
                 :style="{'color': setColor(list.status)}">
              <span>{{list.status}}</span>
              <div class="status-circle" :style="{'background': setColor(list.status)}"></div>
            </div>
            <div class="staff__list-li recording-date">{{list.recordingDate | editDate(isMob)}}</div>
            <div class="staff__list-li pass-date">{{list.passDate | editDate(isMob)}}</div>
          </div>
          <div class="staff__list-departments-btn list__people--hover">
            <button class="staff__list-btn">
              <svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 12 12" fill="none">
                <path d="M3.705 11.295L1.915 9.5H12V8.5H1.915L3.705 6.705L3 6L0 9L3 12L3.705 11.295ZM12 3L9 0L8.295 0.705L10.085 2.5H0V3.5H10.085L8.295 5.295L9 6L12 3Z" fill="#E31243"/>
              </svg>
            </button>
            <button class="staff__list-btn" @click="delStaff(dep, list.id)">
              <svg width="11" height="14" viewBox="0 0 11 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M10.8889 0.777778H8.16667L7.38889 0H3.5L2.72222 0.777778H0V2.33333H10.8889V0.777778ZM0.777778 12.4444C0.777778 12.857 0.941666 13.2527 1.23339 13.5444C1.52511 13.8361 1.92077 14 2.33333 14H8.55556C8.96811 14 9.36378 13.8361 9.6555 13.5444C9.94722 13.2527 10.1111 12.857 10.1111 12.4444V3.5H0.777778V12.4444Z" fill="#E31243"/>
              </svg>
            </button>
            <button class="staff__list-btn" >
              <svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 10 10" fill="none">
                <path d="M3.81923e-07 5.63131L4.92305e-07 4.36869L7.57576 4.36869L4.10354 0.896464L5 -4.37114e-07L10 5L5 10L4.10354 9.10353L7.57576 5.63131L3.81923e-07 5.63131Z" fill="#128BE3"/>
              </svg>
            </button>
          </div>
        </li>
      </ul>
    </div>

  </div>
</section>
</template>

<script>
import MyCheckbox from "@/components/MyCheckbox";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Staff",
  components: {MyCheckbox},

  data:()=>({
    isMob: false,
    width: null,
    company: {
      name: 'ООО «Модуль»',
      img: require('../assets/company_logo.png')
    },
    search: '',
    allCheckbox: false,
    departments: [
      {
        id: 1,
        name: 'Отдел продаж',
        code: 'sales_department',
        isOpen: false,
        staff:[
          {
            id: 1,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Кладовщик',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
          {
            id: 2,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Главный кладовщик',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
          {
            id: 3,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Водитель',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
          {
            id: 4,
            isCheck: false,
            fio: 'Петров Петр Петрович',
            position: 'Водитель',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
        ]
      },
      {
        id: 2,
        name: 'Склад',
        code: 'stock',
        isOpen: false,
        staff:[
          {
            id: 1,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Кладовщик',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
          {
            id: 2,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Главный кладовщик',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
          {
            id: 3,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Водитель',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
          {
            id: 4,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Водитель',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
          {
            id: 5,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Кладовщик',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
          {
            id: 6,
            isCheck: false,
            fio: 'Иванов Иван Иванович',
            position: 'Кладовщик',
            status: 'Проходит',
            recordingDate: '05.09.2022',
            passDate: '05.09.2022',
          },
        ]
      },
    ]
  }),
  filters: {
    editDate: function (value, isMob) {
      if (!value) return ''
      value = value.toString()
      return isMob ? value.slice(1,6)+value.split('.')[2].slice(2) : value
    }
  },
  created() {
    window.addEventListener('resize', this.updateWidth);
   this.isMob =  window.innerWidth < 860
  },
  methods:{
    setColor(item){
      if(item === 'Проходит'){
        return '#FF8800'
      }
    },
    updateWidth() {
      this.width = window.innerWidth;
    },
    setOpen(item){
      this.departments.forEach(el=>{
        if(el.id === item.id){
          el.isOpen = !el.isOpen
        }
      })
    },
    selectAll(){
      this.departments.forEach(item=>{
        item.staff.forEach(el=>{
          el.isCheck = this.allCheckbox
        })
      })
    },
    delStaff(dep, id){
      console.log(dep, id)
      this.departments.forEach(item=>{
        if(dep.id === item.id){
         item.staff = item.staff.filter(el=>el.id !== id)
        }
      })
    }
  },
  computed:{
    getDepFilter(){
      return this.departments.map(item=>{
        return {...item, staff: item.staff.filter(el=>el.fio.toLowerCase().includes(this.search.toLowerCase()))}
      })
    }
  },
  watch:{
    allCheckbox(){
      this.selectAll()
    },
    width(){
      this.isMob = this.width < 860
    }
  }
}
</script>

<style lang="scss">
@import "../style/staff.scss";
</style>
