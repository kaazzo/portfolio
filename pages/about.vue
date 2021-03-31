<template>
  <v-container fuild>
    <v-row>
      <v-col>
        <v-card outlined>
          <v-card-title class="headline font-weight-bold">
            Profile
          </v-card-title>
          <v-card-title>Name: kaazzo</v-card-title>
          <v-card-text>
            アプリケーションエンジニア。<br />
            主に業務系アプリケーションの設計・開発を担当。
            <br />
            フロントよりもバックエンドが好き。 <br />
          </v-card-text>
          <v-card-title>Certification </v-card-title>
          <v-card-text
            >応用情報技術者 <br />セキュリティマネージメント</v-card-text
          >
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-card outlined>
          <v-card-title class="headline font-weight-bold">
            Likes
          </v-card-title>
          <v-card-title>Techs</v-card-title>
          <v-card-text>
            <v-chip
              v-for="(item, i) in favorite"
              :key="i"
              class="ma-2"
              label
              color="primary"
            >
              {{ item }}
            </v-chip>
          </v-card-text>
          <v-card-title>Interests </v-card-title>
          <v-card-text>
            <v-chip
              v-for="(item, i) in likes"
              :key="i"
              class="ma-2"
              label
              color="secondary"
            >
              {{ item }}
            </v-chip>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-card outlined>
          <v-container>
            <v-card-title class="headline font-weight-bold">
              Timeline
            </v-card-title>
            <v-timeline>
              <v-timeline-item v-for="(year, i) in timelines" :key="i">
                <span slot="opposite" class="headline font-weight-bold">
                  {{ year.year }}
                </span>
                <v-card class="elevation-2">
                  <v-card-title class="headline">
                    {{ year.title }}
                  </v-card-title>
                  <v-card-text>
                    {{ year.description }}
                  </v-card-text>
                </v-card>
              </v-timeline-item>
            </v-timeline>
          </v-container>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    favorite: ['Spring Boot', 'Vue.js', 'Docker', 'VSCode', 'Typora'],
    likes: [
      '音楽',
      'ロック',
      'ベース',
      '野球観戦',
      '西武ライオンズ',
      'スニーカー'
    ],
    timelines: [
      {
        year: '2017',
        title: '某実証実験用システム及びポータルサイト開発',
        description:
          '実装・テスト・保守を担当(フロントエンド&バックエンド)。がちがちのウォータフォール。キャリアスタートのPJにて数カ月間の炎上を経験。'
      },
      {
        year: '2018',
        title: '某パブリックサービスのポータルサイト開発',
        description:
          '要件定義・設計・結合試験までを担当(フロントエンド&バックエンド)。比較的大所帯のPJで、チームの何たるかを学ぶ。'
      },
      {
        year: '2020',
        title: '某サービスのポータルサイト開発',
        description:
          '要件定義・設計・結合試験・保守を担当(フロントエンド&バックエンド)。前の案件から一転して、設計～保守まで一人で担当。'
      },
      {
        year: '2021',
        title: '某RPA導入支援',
        description: '現在、RPA導入の案件の要件定義とともにRPA学習中。'
      }
    ]
  })
}
</script>
