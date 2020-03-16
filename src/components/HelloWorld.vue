<template>
  <v-container fluid>
    <v-layout row wrap>
      <v-flex xs12 sm6 md4 lg3 v-for="grade in grades" :key="grade.index">
        <v-card class="mx-auto mb-4" max-width="344">
          <v-img :src="grade.thumb" height="200px"></v-img>

          <v-card-title class="text-wrap">
            {{ grade.curso }}
          </v-card-title>

          <v-card-subtitle>
            {{ grade.modalidade }}
          </v-card-subtitle>

          <v-card-subtitle>
            Inscrições: {{ grade.inscricoes }}
          </v-card-subtitle>

          <v-card-actions>
            <v-btn
              text
              href="http://www.gestoreducacional.com.br/EVENTOS/Inscricao/Ficha_Inscricao.asp?codEmpresa=147&CodGrupo=9&TipoEvento=EV"
              >Inscrever-se</v-btn
            >

            <v-spacer></v-spacer>

            <v-btn icon @click="grade.show = !grade.show">
              Saiba Mais
              <v-icon>{{
                show ? "mdi-chevron-up" : "mdi-chevron-down"
              }}</v-icon>
            </v-btn>
          </v-card-actions>

          <v-expand-transition>
            <div v-show="grade.show">
              <v-divider></v-divider>

              <v-card-text>
                <p><strong>Realização:</strong> {{ grade.realizacao }}</p>
                <p><strong>Público-Alvo:</strong> {{ grade.publico }}</p>
                <p>
                  <strong>Conteúdo Programático:</strong>{{ grade.conteudo }}
                </p>
                <p><strong>Docente:</strong> {{ grade.docente }}</p>
                <p><strong>Carga Horária:</strong> {{ grade.carga }}</p>
              </v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function() {
    return {
      grades: [
        {
          curso: "Comunicação Organizacional Interna",
          modalidade: "A Distância - EAD",
          inscricoes: "17.03.2020 a 31.03.2020",
          realizacao: "03.04.2020 a 28.05.2020",
          conteudo:
            "Comunicação Empresarial: Conceito, Aplicação e Importância; Comunicação Interna Nas Organizações; Instrumentos de Comunicação; Comunicação Verbal e Não Verbal.",
          docente: "Karina Ribeiro Modesto",
          carga: "40h",
          vagas: 40,
          evento: "Gratuito",
          show: false,
          publico:
            "Gestores, Membros de Organizações,  Candidatos aos Cursos de Adiministração, Ciências Contábeis, Gestão Financeira e Processos Gerenciais",
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Comunicacao_Organizacional.jpg"
        },
        {
          curso: "Introdução à Educação a Distância",
          modalidade: "A Distância - EAD",
          inscricoes: "17.03.2020 a 31.03.2020",
          realizacao: "03.04.2020 a 28.05.2020",
          conteudo:
            "Educação a Distância: Bases Conceituais e Evolução Histórica; Ambientes Virtuais de Aprendizagem (AVA); Perfil e Atribuições do Professor, do Tutor e do Aluno na Educação a Distância; Aprendizagem a Distância; Avaliação da Aprendizagem.",
          docente: "Breno Silva de Abreu",
          carga: "40h",
          vagas: 40,
          evento: "Gratuito",
          show: false,
          publico: "Docentes, Tutores e Candidatos ao Curso de Pedagogia",
          thumb: "http://portal.facesa.com.br/img/cursos_img/Intro_EaD.jpg"
        },
        {
          curso: "Sistemas de Informações Gerenciais",
          modalidade: "A Distância - EAD",
          inscricoes: "17.03.2020 a 31.03.2020",
          realizacao: "03.04.2020 a 28.05.2020",
          conteudo:
            "Introdução aos Sistemas de Informação; Sistemas Especialistas; Banco de Dados, Datawarehouse e Business Intelligence; Big Data e Internet das Coisas (IoT).",
          docente: "Karina Ribeiro Modesto",
          carga: "40h",
          vagas: 40,
          evento: "Gratuito",
          show: false,
          publico: "Docentes, Tutores e Candidatos ao Curso de Pedagogia",
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Sistema_Info_Gerencial.jpg"
        },
        {
          curso: "Técnicas de Mapeamento de Processos",
          modalidade: "A Distância - EAD",
          inscricoes: "17.03.2020 a 31.03.2020",
          realizacao: "03.04.2020 a 28.05.2020",
          conteudo:
            "Mapeamento de processos; Ciclo de Vida de um Processo; Planejar o BPM; Indicadores de Processos; Processos na Melhoria Contínua.",
          docente: "Karina Ribeiro Modesto",
          carga: "40h",
          vagas: 40,
          evento: "Gratuito",
          show: false,
          publico:
            "Gestores e  Candidatos aos Cursos de Adiministração, Ciências Contábeis, Gestão Financeira e Processos Gerenciais",
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Process_Mapping.jpg"
        },
        {
          curso: "Educação, Corpo e Movimento",
          modalidade: "A Distância - EAD",
          inscricoes: "17.03.2020 a 31.03.2020",
          realizacao: "03.04.2020 a 28.05.2020",
          conteudo:
            "Linguagem Corporal; Corpo e Movimento; Introdução à Recreação e ao Lazer; Ludicidade: O Jogo e a Brincadeira.",
          docente: "Karina Ribeiro Modesto",
          carga: "40h",
          vagas: 40,
          evento: "Gratuito",
          show: false,
          publico:
            "Gestores e  Candidatos aos Cursos de Adiministração, Ciências Contábeis, Gestão Financeira e Processos Gerenciais",
          thumb: "http://portal.facesa.com.br/img/cursos_img/Ed_Mov.jpg"
        }
      ]
    };
  }
};
</script>
<style scoped>
.v-card__text,
.v-card__title {
  word-break: normal !important ;
}
</style>
