<template>
  <section>
    <nav class="navbar navbar-light bg-light menu-superior">
      <div class="container">
        <router-link class="navbar-brand fw-bold" to="/home"
          >SwAdmin</router-link
        >
        <div class="navbar-nav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a class="nav-link" href="#">Sair</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <div class="d-flex">
      <div class="list-group menu-esquerda">
        <router-link
          class="list-group-item list-group-item-action"
          exact-active-class="active-link"
          to="/home/dashboard"
          ><i class="bi bi-speedometer2"></i> Dashboard
        </router-link>
        <router-link
          class="list-group-item list-group-item-action"
          to="/home/vendas"
          exact-active-class="active-link"
          ><i class="bi bi-cart"></i> Vendas
        </router-link>
        <router-link
          class="list-group-item list-group-item-action"
          :to="{ name: 'leads-sales' }"
          exact-active-class="active-link"
          ><i class="bi bi-caret-right"></i> Leads
        </router-link>
        <router-link
          class="list-group-item list-group-item-action"
          :to="{ name: 'contract-sales' }"
          exact-active-class="active-link"
          ><i class="bi bi-caret-right"></i> Contratos
        </router-link>
        <router-link
          class="list-group-item list-group-item-action"
          :to="{ name: 'services' }"
          exact-active-class="active-link"
          ><i class="bi bi-card-checklist"></i> Serviços
        </router-link>
      </div>

      <div class="w-100">
        <nav aria-label="breadcrumb" class="pt-1 ps-3">
          <ol class="breadcrumb">
            <li class="breadcrumb-item text-secondary" aria-current="page">
              Dashboard
            </li>
          </ol>
        </nav>

        <div class="container-fluid">
          <router-view></router-view>
        </div>
      </div>
    </div>

    <div class="footer text-center">
      <router-view name="footer"></router-view>
      <!-- rodapé -->
    </div>
  </section>
</template>


<script>
export default {
  name: "Home",
};
</script>

<style scoped>
.menu-superior {
  border-bottom: solid 1px #ccc;
}

.menu-esquerda {
  border-right: solid 1px #ccc;
  width: 250px;
}

.list-group-item {
  border-top: none;
  border-right: none;
}

.active-link {
  color: #fff;
  background-image: linear-gradient(to right, orange 60%, #ccc);
  border-color: #ccc;
}

.footer {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  background: orange;
}
</style>
