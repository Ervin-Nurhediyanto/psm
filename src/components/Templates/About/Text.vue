<template>
  <div class="row-xl h-95vh d-flex justify-content-center align-items-center">
    <div class="col-12 col-sm-12 col-md-8 col-xl-10 px-0">
      <!-- <div class="h-100 w-100 mt-2 p-3 shadow rounded bg-dark-grey"> -->
      <div class="h-100 w-100 mt-2 p-3 shadow rounded bg-aqua">
      <div class="mt-1 mb-3">{{ data.text.intro }}</div>
        <div class="my-3">{{ data.text.create }}</div>
        <div class="my-3">{{ data.text.list }}</div>
        <div class="row">
          <div class="col-3 p-0">
            <ul v-for="index in data.members.length" :key="index">
              <li class="li-none">{{ data.members[index - 1].name }}</li>
            </ul>
          </div>
          <div class="col-3 p-0">
            <ul v-for="index in data.members.length" :key="index">
              <li class="li-none">{{ data.members[index - 1].nim }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'T-About-Text',
  data () {
    return {
      data: {
        members: [
          {
            name: 'Ervin Nurhediyanto',
            nim: '(1722600016)'
          },
          {
            name: 'Rizki Umami',
            nim: '(1721600025)'
          },
          {
            name: 'Muhammad Doni Irawan',
            nim: '(1721600020)'
          },
          {
            name: 'Selvia Isnaeni',
            nim: '(1721600015)'
          },
          {
            name: 'Nanda Fatia Dewi',
            nim: '(1721600023)'
          },
          {
            name: 'Lulu Niswatun',
            nim: '(1721600017)'
          },
          {
            name: 'Salsabila Nur Aurora',
            nim: '(1721600024)'
          },
          {
            name: 'Aenun Wahyuningrum',
            nim: '(1721600021)'
          },
          {
            name: 'Nur Afifah',
            nim: '(1721600030)'
          },
          {
            name: 'Putri Rahmatul Awalia',
            nim: '(1721600027)'
          }
        ],
        owner: {
          name: 'Ervin Nurhediyanto',
          nim: '1722600016'
        },
        text: {
          intro: 'PSM (Program Simpleks Method) adalah aplikasi yang dirancang untuk mempermudah penyelesaian program linear pada metode simpleks. Aplikasi ini masih dalam tahap pengembangan sehingga hanya terbatas pada penyelesaian dengan metode simpleks primal.',
          create: 'Aplikasi ini dibuat oleh mahasiswa Pendidikan Matematika Universitas Pancasakti Tegal untuk memenuhi tugas Mata Kuliah Program Linear dengan dosen pengampu AHMADI, S.Pd.,M.Si.',
          list: 'Anggota Kelompok:'
        }
      }
    }
  }
}
</script>
