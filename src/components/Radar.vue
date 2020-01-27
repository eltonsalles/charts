<template>
  <div>
    <canvas class="radar" ref="radar"></canvas>
  </div>
</template>

<script>
import Charts from 'chart.js';

export default {
  name: 'radar',

  data() {
    return {
      chartRadar: null,
      options: {
        title: {
          display: true,
          text: 'Animes com mais episódios',
        },
        legend: {
          display: false,
        },
        scale: {
          angleLines: {
            display: false,
          },
          ticks: {
            display: false,
          },
          gridLines: {
            color: 'rgba(255, 255, 255, 1)',
            lineWidth: 0.2,
          },
          pointLabels: {
            fontSize: 10,
          },
        },
        tooltips: {
          callbacks: {
            label: function f(tooltipItem, data) {
              let label = data.labels[tooltipItem.index] || '';

              if (label) {
                label += ': ';
              }
              label += Math.round(tooltipItem.value * 100) / 100;
              return label;
            },
          },
        },
      },
      data: {
        labels: [
          'A Penguin’s Troubles.',
          'Astro Boy.',
          'Atashin’chi',
          'Bleach',
          'Charady no Joke na Mainichi',
          'Chibi Maruko-chan',
          'Cooking Idol I! My! Mine!',
          'Crayon Shin-chan',
          'Detective Conan',
          'Doraemon (1979)',
          'Doraemon (2005)',
          'Dotanba no Manners.',
          'Dr. Slump Arale-chan.',
          'Dragon Ball Z.',
          'Fairy Tail.',
          'Folktales from Japan.',
          'Gatapishi.',
          'Gintama',
          'Hamtaro',
          'Hana Kappa',
          'Hoka Hoka Kazoku',
          'Holly the Ghost.',
          'Hoshi no Ko Poron.',
          'Hyppo and Thomas',
          'Ikkyū-san',
          'Itazura tenshi Chippo-chan.',
          'Katekyō Hitman Reborn!',
          'Keroro Gunso',
          'Kirin Ashita no Calendar',
          'Kirin Monosjiri Daigaku: Manga Jinbutsushi.',
          'Kirin no Monoshiri Yakata',
          'Kiteretsu Daihyakka',
          '"Kochira Katsushika-ku',
          'Kameari Kōen-mae Hashutsujo"',
          'Kotowaza House',
          'Let’s Go COOKR’n.',
          'Manga Hajimete Monogatari.',
          'Manga Nippon Mukashi Banashi.',
          'Miracle! Mimika.',
          'Monoshiri Daigaku Ashita no Calendar.',
          'Naruto: Shippuden',
          'Naruto.',
          'Ninja Hattori-kun',
          'Nintama Rantarō',
          'Obake no Q-tarō',
          'Ojarumaru',
          'One Piece',
          'Otogi Manga Calendar',
          'Oyako Club',
          'Parasol Henbee.',
          'Perman',
          'Pokémon (original series)',
          'Pokémon: Advanced Generation.',
          'Sazae-san',
          'Sekai Monoshiri Ryokō',
          'Shima Shima Tora no Shimajirō.',
          'Shimajiro no Waow.',
          'Soreike! Anpanman',
          'Tamagon the Counselor.',
          'Urusei Yatsura.',
          'Yu-Gi-Oh! Duel Monsters.',
        ],
        datasets: [
          {
            label: 'Episódios',
            fill: true,
            backgroundColor: 'rgba(255,0,0,0.2)',
            borderColor: 'rgba(255,0,0,1)',
            pointBorderColor: '#ff0000',
            pointBackgroundColor: 'rgba(255,0,0,1)',
            data: [
              253,
              193,
              330,
              366,
              365,
              1075,
              400,
              911,
              837,
              1787,
              810,
              283,
              243,
              291,
              277,
              238,
              199,
              316,
              296,
              430,
              1428,
              200,
              260,
              300,
              296,
              240,
              203,
              358,
              1498,
              366,
              1565,
              331,
              373,
              773,
              196,
              305,
              1488,
              225,
              1274,
              481,
              220,
              696,
              1948,
              510,
              1596,
              762,
              312,
              1818,
              200,
              526,
              276,
              193,
              191,
              1006,
              726,
              235,
              1331,
              195,
              195,
              224,
            ],
          },
        ],
      },
    };
  },

  methods: {
    init() {
      this.chartRadar = new Charts(this.$refs.radar, {
        type: 'radar',
        data: this.data,
        options: this.options,
      });
    },
  },

  mounted() {
    this.init();
  },
};
</script>

<style lang="scss" scoped>
.radar {
  background-color: #000000;
}
</style>
