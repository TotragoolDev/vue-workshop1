<template>
  <v-card class="card" rounded="xl" elevation="3">

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
              small outlined
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
              <dt>ที่ทำงาน</dt><dd>บริษัท อินเทอร์เน็ตประเทศไทย จำกัด</dd>
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
            สวัสดีครับ ผมชื่อ เจ๋ง อายุ 22 ปี จบจากมหาวิทยาลัยเทคโนโลยีสุรนารี สาขาวิศวกรคอมพิวเตอร์ครับ       </v-card-text>

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

    </v-card>
</template>

<script>
export default {
  name: 'ProfileCard',
  
    data() {
     return {

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
          { label: 'ดูฟุตบอล', icon: 'mdi-soccer' },
          { label: 'เล่นเกม', icon: 'mdi-controller' },
          { label: 'ดูหนังและซีรี่ย์', icon: 'mdi-movie-open-outline' },
          { label: 'ฟังเพลง', icon: 'mdi-music-note' },
        ],
      }
    },
}
</script>
<style scoped>
  .card {
    max-width: 700px;
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
    margin-bottom: 6.5px;
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