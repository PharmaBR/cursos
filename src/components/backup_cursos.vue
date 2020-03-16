<template>
  <v-container fluid>
    <v-layout row wrap>
      <v-flex xs12 sm6 md4 lg3 v-for="grade in grades" :key="grade.index">
        <v-card class="mx-auto" max-width="344">
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
            <v-btn text>Inscrever-se</v-btn>

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
          curso: "Ações Inclusivas de Estudantes",
          modalidade: "A Distância - EAD",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "30.01.2020 a 06.02.2020",
          conteudo:
            "Aspectos Históricos e Legais; Conceitos; Inclusão e Educação.",
          docente: "Flávia Pinheiro Della Giustina",
          carga: "40h",
          vagas: 70,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Acoes_Inclusivas.jpg"
        },
        {
          curso: "Criação e Atualização Sistemática de Currículo Lattes",
          modalidade: "A Distância - EAD",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "30.01.2020 a 06.02.2020",
          conteudo:
            "Plataforma Lattes: Conceitos; Criação do Currículo Lattes; Preenchimento do Currículo Lattes; Atualização e Manutenção do Currículo Lattes.",
          docente: "Rodrigo Marques da Silva",
          carga: "40h",
          vagas: 70,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Criacao_e_Atualizacao.jpg"
        },
        {
          curso: "Docente Empreendedor: Criação de Cursos On-line",
          modalidade: "A Distância - EAD",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "30.01.2020 a 06.02.2020",
          conteudo:
            "Nicho de Atuação; Criação de Material Didático Multimídia; Noções Básicas de Didática de EaD; Divulgação do Curso; Comunicação Com os Alunos.",
          docente: "Breno Silva de Abreu",
          carga: "40h",
          vagas: 70,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Docente_Empreendedor.jpg"
        },
        {
          curso: "Introdução à Educação a Distância",
          modalidade: "A Distância - EAD",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "30.01.2020 a 06.02.2020",
          conteudo:
            "Educação a Distância: Bases Conceituais e Evolução Histórica; Ambientes Virtuais de Aprendizagem (AVA);Perfil e Atribuições do Professor, do Tutor e do Aluno na Educação a Distância; Aprendizagem a Distância; Avaliação da Aprendizagem.",
          docente: "Karina Ribeiro Modesto",
          carga: "50h",
          vagas: 70,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Introducao_a_Educacao.jpg"
        },
        {
          curso: "Metodologias Ativas na Educação a Distância",
          modalidade: "A Distância - EAD",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "30.01.2020 a 06.02.2020",
          conteudo:
            "Fundamentação Teórica; Metodologias Ativas na Educação a Distância; Estratégias, Métodos e Técnicas; Ambiente de Interação e Colaboração.",
          docente: "Fernando Vianna Cabral Pucci",
          carga: "40h",
          vagas: 70,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Metodologias_Ativas.jpg"
        },
        {
          curso: "Moodle Para Docente: Módulo I",
          modalidade: "Presencial",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "31.01.2020 - 09:30 às 12:30",
          conteudo:
            "Visão Geral do Moodle; Gerenciamento de Blocos e Configurações; Utilização de Recursos: Arquivos, Documentos, Apresentação e Links; Utilização de Atividades: Fóruns, Chat, Escolha, Glossário e Tarefas; Criação de Questionário e Banco de Questões; Notas; Progresso de Discente.",
          docente: "Breno Silva de Abreu",
          carga: "3h",
          vagas: 75,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Moodle_Para_Docente.jpg"
        },
        {
          curso: "Primeiros Socorros",
          modalidade: "Presencial",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "31.01.2020 - 14:00 às 18:00",
          conteudo:
            "Introdução a Primeiros Socorros; Primeiros Socorros em Convulsões; Primeiros Socorros em Desmaios; Primeiros Socorros em Engasgos; Técnica de Ressuscitação Cardiopulmonar.",
          docente: "Rennan MirandaTavares",
          carga: "4h",
          vagas: 85,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Primeiros_Socorros.jpg"
        },
        {
          curso: "Programa de Monitoria Acadêmica da FACESA",
          modalidade: "A Distância - EAD",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "30.01.2020 a 06.02.2020",
          conteudo:
            "O Que é Monitoria Acadêmica; Competências do Monitor; Papel do Orientador; Contribuição da Monitoria Para o Processo de Ensino e Aprendizagem; Funcionamento do Programa de Monitoria Acadêmica na FACESA.",
          docente: "Haline Gerica de Oliveira Alvim",
          carga: "40h",
          vagas: 70,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Programa_de_Monitoria.jpg"
        },
        {
          curso: "Programa de Qualificação de Avaliação",
          modalidade: "A Distância - EAD",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "30.01.2020 a 06.02.2020",
          conteudo:
            "Explorando a Página do NAP/NAQ; Programa de Qualificação de Avaliação; Capa Padrão de Avaliação; Ambiente de Submissão de Avaliação; Cadastro na Plataforma de Submissão de Avaliação; Introdução às Modalidades de Avaliação: Diagnóstica, Formativa e Somativa.",
          docente: "Karina Ribeiro Modesto",
          carga: "40h",
          vagas: "Ilimitadas",
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Programa_de_Qualificacao.jpg"
        },
        {
          curso:
            "Submissão de Artigos Científicos nas Plataformas OJS e Scholar One",
          modalidade: "A Distância - EAD",
          inscricoes: "16.12.2019 a 31.01.2020",
          realizacao: "30.01.2020 a 06.02.2020",
          conteudo:
            "Introdução às Plataformas OJS e Scholar One; Submissão de Artigos Científicos na Plataforma OJS; Submissão de Artigos Científicos na Scholar One.",
          docente: "Rodrigo Marques da Silva",
          carga: "30h",
          vagas: 70,
          evento: "Gratuito",
          show: false,
          thumb:
            "http://portal.facesa.com.br/img/cursos_img/Submissao_de_Artigos.jpg"
        }
      ]
    };
  }
};
</script>
<style scoped>
.v-card__text,
.v-card__title {
  word-break: normal; /* maybe !important  */
}
</style>
