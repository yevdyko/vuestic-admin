<template>
  <div class="filters-page">
    <div class="row">
      <div class="col-md-12">
        <vuestic-widget :headerText="$t('filters.headings.show')">
          <vuestic-tag-group v-model="tags"/>
        </vuestic-widget>
      </div>
    </div>
    <div class="row">
      <div class="col-md-12">
        <vuestic-widget>
          <vuestic-data-table
            :apiUrl="apiUrl"
            :tableFields="tableFields"
            :itemsPerPage="itemsPerPage"
            :defaultPerPage="defaultTablePerPage"
            :sortFunctions="sortFunctions"
            :apiMode="apiMode"
            :paginationPath="paginationPath"
            :queryParams="queryParams"
          >
            <spring-spinner
              slot="loading"
              :animation-duration="2500"
              :size="70"
              color="#4ae387"
            />
          </vuestic-data-table>
        </vuestic-widget>
      </div>
    </div>
  </div>
</template>

<script>
  import FieldsDef from 'vuestic-components/vuestic-datatable/data/fields-definition'
  import ItemsPerPageDef from 'vuestic-components/vuestic-datatable/data/items-per-page-definition'
  import QueryParams from 'vuestic-components/vuestic-datatable/data/query-params'
  import {SpringSpinner} from 'epic-spinners'

  export default {
    name: 'filters',
    components: {
      SpringSpinner
    },
    data () {
      return {
        apiUrl: 'https://vuetable.ratiw.net/api/users',
        apiMode: true,
        tableFields: FieldsDef.tableFields,
        itemsPerPage: false,
        sortFunctions: FieldsDef.sortFunctions,
        paginationPath: false,
        queryParams: QueryParams
      }
    }
  }
</script>
