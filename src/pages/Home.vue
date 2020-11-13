<template>
  <v-container>
    <h2 class="cte">Status Geração Automática CT-e</h2>
    <v-card class="status " width="100%">
      <v-card-title color="blue">
        Informe algum filtro
      </v-card-title>

      <v-form class="status__form d-flex flex-column flex-wrap pa-5">
        <v-row>
          <v-col md="2">
            <v-text-field
              label="N° Nota Fiscal"
              outlined
              required
              hide-details
            ></v-text-field>
          </v-col>
          <v-col md="2">
            <v-text-field
              label="Código de agendamento"
              outlined
              required
              hide-details
            ></v-text-field>
          </v-col>
          <v-col md="2">
            <v-text-field
              outlined
              hide-details
              label="Selecione o período"
              prepend-inner-icon="today"
              append-icon="cancel"
            ></v-text-field>
          </v-col>
          <v-col md="5">
            <v-text-field
              outlined
              label="Cliente"
              hide-details
              prepend-inner-icon="cloud"
              append-icon="cancel"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row class="d-flex align-center pb-3">
          <v-col md="2">
            <v-autocomplete
              label="Empresa"
              hide-details
              outlined
              item-text="Descricao"
              item-value="Pendencia_Id"
            >
            </v-autocomplete>
          </v-col>
          <v-col md="2">
            <v-autocomplete
              label="Ponto de operação"
              hide-details
              outlined
              item-text="Descricao"
              item-value="Pendencia_Id"
            >
            </v-autocomplete>
          </v-col>

          <v-col md="2">
            <v-autocomplete
              label="Mensagem"
              hide-details
              outlined
              item-text="Descricao"
              item-value="Pendencia_Id"
            >
            </v-autocomplete>
          </v-col>
          <v-col md="2">
            <v-switch
              class="pl-5"
              v-model="ex11"
              label="Atualizar a cada"
              color="info"
              value="info"
              hide-details
            ></v-switch>
          </v-col>
          <v-col md="1">
            <v-text-field
              hide-details
              label="2"
              outlined
              class="text-center"
            ></v-text-field>
          </v-col>
          <spam>minutos.</spam>
        </v-row>
        <v-divider></v-divider>
        <div>
          <v-btn
            color="primary"
            class="status__form__button mt-5"
            rounded
            elevation="0"
            type="submit"
            >Pesquisar</v-btn
          >
          <v-btn
            outlined
            color="primary"
            class="status__form__button ml-3 mt-5"
            rounded
            elevation="0"
            >Voltar</v-btn
          >
        </div>
      </v-form>
    </v-card>
    <Filter />
    <v-card class="list pl-7 mt-5">
      <v-card-title class="list__processing">
        <v-icon class="mr-3" color="#D69A00">
          warning
        </v-icon>
        Processamento pendente: Aguardando dados das notas fiscais.
      </v-card-title>
      <v-card-title>
        Lista
      </v-card-title>

      <v-data-table
        :headers="headers"
        :items="invoice"
        :items-per-page="5"
        :single-select="singleSelect"
        class="elevation-0"
        item-key="note"
        show-select
        v-model="selected"
      ></v-data-table>
    </v-card>
    <div>
      <v-btn class=" mt-5" color="#C9C9C9" rounded elevation="0" type="submit"
        >Agendar</v-btn
      >
    </div>
  </v-container>
</template>

<style lang="stylus"></style>
<script>
// @ is an alias to /src
import Filter from "@/components/Filter";

export default {
  data() {
    return {
      selected: [],
      checkbox: false,
      singleSelect: false,
      headers: [
        {
          sortable: true,
          text: "Nota Fiscal",
          align: "left",
          value: "note",
        },
        { text: "N° Carga", value: "charge" },
        { text: "Cliente", value: "client" },
        { text: "Origem", value: "origin" },
        { text: "Destino", value: "destiny" },
        { text: "Data/Hora", value: "dateHour" },
        { text: "Mensagem", value: "message" },
      ],
      invoice: [
        {
          note: "1001",
          charge: "0001",
          client: "",
          origin: "",
          destiny: "",
          dateHour: "",
          message: "Nota incompleta",
        },
        {
          note: "1002",
          charge: "0001",
          client: "",
          origin: "",
          destiny: "",
          dateHour: "",
          message: "Nota incompleta",
        },
        {
          note: "1003",
          charge: "0001",
          client: "Signa",
          origin: "São Paulo - SP",
          destiny: "São Paulo - SP",
          dateHour: "15/07/209 - 18:05 : 32",
          message: "",
        },
        {
          note: "1004",
          charge: "0001",
          client: "Signa",
          origin: "São Paulo - SP",
          destiny: "São Paulo - SP",
          dateHour: "15/07/209 - 18:05 : 32",
          message: "",
        },
        {
          note: "1005",
          charge: "0001",
          client: "Signa",
          origin: "São Paulo - SP",
          destiny: "São Paulo - SP",
          dateHour: "15/07/209 - 18:05 : 32",
          message: "",
        },
        {
          note: "1006",
          charge: "0001",
          client: "Signa",
          origin: "São Paulo - SP",
          destiny: "São Paulo - SP",
          dateHour: "15/07/209 - 18:05 : 32",
          message: "",
        },
        {
          note: "1007",
          charge: "0001",
          client: "Signa",
          origin: "São Paulo - SP",
          destiny: "São Paulo - SP",
          dateHour: "15/07/209 - 18:05 : 32",
          message: "",
        },
        {
          note: "1008",
          charge: "0001",
          client: "Signa",
          origin: "São Paulo - SP",
          destiny: "São Paulo - SP",
          dateHour: "15/07/209 - 18:05 : 32",
          message: "",
        },
        {
          note: "1009",
          charge: "0001",
          client: "Signa",
          origin: "São Paulo - SP",
          destiny: "São Paulo - SP",
          dateHour: "15/07/209 - 18:05 : 32",
          message: "",
        },
        {
          note: "1010",
          charge: "0001",
          client: "Signa",
          origin: "São Paulo - SP",
          destiny: "São Paulo - SP",
          dateHour: "15/07/209 - 18:05 : 32",
          message: "",
        },
      ],
    };
  },

  components: {
    Filter,
  },
};
</script>
<style lang="scss" scoped>
.cte {
  color: #0169ce;
  margin: 20px 0 20px;
  font-size: 33px;
}
.status {
  padding-bottom: 10px;
  &__form {
    width: 100%;

    &__button {
      font-size: 14px;
      font-weight: 500;
      font-style: normal;
      width: 113px;
    }
  }
}
.list {
  &__processing {
    display: flex;
    justify-content: center;
    color: #d69a00;
    font-size: 20px;
  }
}
</style>
