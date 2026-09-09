<template>
<div>
  <v-card class="card" rounded="sm" elevation="3">

    <v-row>

      <v-col cols="12" sm="5">

        <v-img src="/img/spider-profile.jpg" class="image"/>

        <v-card-title>ทักษะ</v-card-title>

        <v-divider class="line" />

        <div class="skills">
          <v-chip
            v-for="skill in skills"
            :key="skill.label"
            small outlined
          >
            {{ skill.label }}
          </v-chip>
        </div>

        <v-card-title>งานอดิเรก</v-card-title>

        <v-divider class="line" />

        <div class="hobbies">
          <v-chip
            v-for="hobby in hobbies"
            :key="hobby.label"
            :href="hobby.href"
            :title="hobby.label"
            target="_blank"
            rel="noopener noreferrer"
            small outlined
            @click="showImages(hobby)"
          >
            <v-icon left small>{{ hobby.icon }}</v-icon>
            {{ hobby.label }}
          </v-chip>
        </div>

      </v-col>

      <v-col cols="12" sm="7">

        <v-card-title>โปรไฟล์</v-card-title>

        <v-divider class="line" />

        <dl class="facts">
          <div class="facts__row">
            <dt>ชื่อ</dt><dd>ต่อตระกูล สืบค้า</dd>
          </div>
          <div class="facts__row">
            <dt>ชื่อเล่น</dt><dd>เจ๋ง</dd>
          </div>
          <div class="facts__row">
            <dt>อายุ</dt><dd>22</dd>
          </div>
          <div class="facts__row">
            <dt>จบจาก</dt><dd>มหาลัยเทคโนโลยีสุรนารี</dd>
          </div>
          <div class="facts__row">
            <dt>สาขา</dt><dd>วิศวกรคอมพิวเตอร์</dd>
          </div>
          <div class="facts__row">
            <dt>ตำแหน่ง</dt><dd>Software Engineer</dd>
          </div>
          <div class="facts__row">
            <dt>ที่ทำงาน</dt><dd>INET</dd>
          </div>
          <div class="facts__row">
            <dt>ทีมฟุตบอลที่เชียร์</dt><dd>Barcelona</dd>
          </div>
          <div class="facts__row">
            <dt>นักเตะที่ชอบ</dt><dd>Lionel Messi</dd>
          </div>
        </dl>

        <v-card-title>เกี่ยวกับผม</v-card-title>

        <v-divider class="line" />

        <v-card-text>
          สวัสดีครับ ผมชื่อ เจ๋ง อายุ 22 ปี จบจากมหาวิทยาลัยเทคโนโลยีสุรนารี สาขาวิศวกรคอมพิวเตอร์ครับ เล่นกีฬาส่วนใหญ่จะเป็นฟุตบอลกับบาสเก็ตบอลเป็นหลักครับ
          ส่วนเกมที่เล่นคือ valorant หนังเรื่องโปรด Harry Potter ซีรี่ย์เรื่องโปรด Game of Thrones เพลงโปรด คือ Love Yourself ของ Justin Bieber ครับ   
        </v-card-text>

        <v-card-title>ช่องทางการติดต่อ</v-card-title>

        <v-divider class="line" />

        <div class="contact">
          <v-btn
            v-for="link in contacts"
            :key="link.label"
            :href="link.href"
            :title="link.label"
            :aria-label="link.label"
            target="_blank"
            rel="noopener noreferrer"
            icon
            small
            class="contact__btn"
          >
            <v-icon size="50">{{ link.icon }}</v-icon>
          </v-btn>
        </div>

      </v-col>

    </v-row>

  <v-dialog v-model="dialog" max-width="600">
    <v-card v-if="selected" rounded="lg">

      <v-window
        :key="selected.label"
        :show-arrows="selected.images.length > 1"
        class="gallery"
      >
        <v-window-item
          v-for="img in selected.images"
          :key="img"
        >
          <v-img :src="img" :alt="selected.label" />
        </v-window-item>
      </v-window>

    </v-card>
  </v-dialog>

  </v-card>
</div>
</template>

<script>
export default {
  name: 'ProfileCard',
  
    data() {
     return {

        dialog: false,
        selected: null,

        skills: [
          { label: 'HTML/CSS' },
          { label: 'JavaScript' },
          { label: 'Git' },
          { label: 'SQL' },
          { label: 'Golang' },
          { label: 'Node.js' },
        ],

        contacts: [
          {
           label: 'อีเมล',
           icon: 'mdi-email-outline',
           href: 'https://mail.google.com/mail/?view=cm&fs=1&to=totragooldev@gmail.com',
          },
          {
           label: 'GitHub',
           icon: 'mdi-github',
           href: 'https://github.com/TotragoolDev',
          },
          {
           label: 'LinkedIn',
           icon: 'mdi-linkedin',
           href: 'https://www.linkedin.com/in/totragool-suebkha-132a90404',
          },
        ],

        hobbies: [
          { label: 'ดูฟุตบอล', 
            icon: 'mdi-soccer',
            images: [
            '/img/Lionel Messi Fc BARCELONA.jpg',
            '/img/Esquadrão Imortal - Barcelona 2014-2017 - Imortais Do Futebol.jpg',
            '/img/LAMINE YAMAL.jpg',
          ], 
          },
          { label: 'เล่นเกม', 
            icon: 'mdi-controller',
            images: [
            '/img/valo.jpg',
          ],  
          },
          { label: 'ดูหนังและซีรี่ย์', 
            icon: 'mdi-movie-open-outline',
            images: [
            '/img/GOT.jpg',
            '/img/HarryPotter.jpg',
          ],
          },
          { label: 'ฟังเพลง', 
            icon: 'mdi-music-note',
            images: [
            '/img/love yourself justin bieber.jpg',
            '/img/the lazy song- bruno mars.jpg',
            '/img/cruel summer taylor swift_.jpg',
          ], 
          },
        ],
      }
    },
    methods: {
    showImages(hobby) {
      this.selected = hobby
      this.dialog = true
      },
    },
}
</script>
<style scoped>
  .card {
    margin: 0 auto;
    padding: 32px 42px;
  }

  .line {
    border-top-width: 3px;
    margin-bottom: 8px;
  }

  .image {
    border-radius: 4px;
  }

  .facts {
    margin-top: 10px;
    margin-left:20px;
    font-size: 15px;
    line-height: 1.9;
  }
 
  .facts__row {
    display: flex;
    gap: 8px;
  }
 
  .facts dt {
    flex: none;
    min-width: 120px;
  }
 
  .facts dt::after {
    content: ' :';
  }
 
  .facts dd {
    margin: 0;
  }

  .contact {
    display: flex;
    justify-content: flex-end;
  }

  .contact__btn {
    padding: 25px;
  }

  .hobbies {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 12px;
    margin-left: 16px;
    margin-bottom: 20px;
  }
</style>