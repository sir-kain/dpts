<template>
  <!-- Dashboard Analytics Start -->
  <no-ssr>
    <section id="dashboard-analytics">
      <div class="row match-height">
        <!-- Greetings Card starts -->
        <div class="col-lg-6 col-md-12 col-sm-12">
          <div class="card card-congratulations">
            <div class="card-body text-center">
              <img
                src="/images/elements/decore-left.png"
                class="congratulations-img-left"
                alt="card-img-left"
              />
              <img
                src="/images/elements/decore-right.png"
                class="congratulations-img-right"
                alt="card-img-right"
              />
              <div class="avatar avatar-xl bg-primary shadow">
                <div class="avatar-content">
                  <i data-feather="award" class="font-large-1"></i>
                </div>
              </div>
              <div class="text-center">
                <h1 class="mb-1 text-white">
                  Bonjour
                  <strong> {{ $auth.user.prenom }} {{ $auth.user.nom }} </strong
                  >,
                </h1>
                <p class="card-text m-auto w-75">
                  Division de la Police Technique et Scientifique
                  <strong>(DPTS)</strong>
                </p>
              </div>
            </div>
          </div>
        </div>
        <!-- Greetings Card ends -->

        <!-- Subscribers Chart Card starts -->
        <div class="col-lg-3 col-sm-6 col-12">
          <div class="card">
            <div class="card-header flex-column align-items-start pb-0">
              <div class="avatar bg-light-primary p-50 m-0">
                <div class="avatar-content">
                  <i data-feather="users" class="font-medium-5"></i>
                </div>
              </div>
              <h2 class="fw-bolder mt-1">92.6k</h2>
              <p class="card-text">Subscribers Gained</p>
            </div>
            <div id="gained-chart"></div>
          </div>
        </div>
        <!-- Subscribers Chart Card ends -->

        <!-- Orders Chart Card starts -->
        <div class="col-lg-3 col-sm-6 col-12">
          <div class="card">
            <div class="card-header flex-column align-items-start pb-0">
              <div class="avatar bg-light-warning p-50 m-0">
                <div class="avatar-content">
                  <i data-feather="package" class="font-medium-5"></i>
                </div>
              </div>
              <h2 class="fw-bolder mt-1">38.4K</h2>
              <p class="card-text">Orders Received</p>
            </div>
            <div id="order-chart"></div>
          </div>
        </div>
        <!-- Orders Chart Card ends -->
      </div>
    </section>
  </no-ssr>
  <!-- Dashboard Analytics end -->
</template>
<script>
export default {
  name: 'HomePage',
  middleware: 'auth',
  head() {
    return {
      title: 'Tableau de board | DPTS',
      link: [
        {
          rel: 'stylesheet',
          type: 'text/css',
          href: '/css/plugins/charts/chart-apex.min.css',
        },
        {
          rel: 'stylesheet',
          type: 'text/css',
          href: '/css/pages/authentication.css',
        },
      ],
      script: [
        { src: '/vendors/js/charts/apexcharts.min.js', defer: true },
        { src: '/js/scripts/pages/dashboard-analytics.min.js', defer: true },
      ],
    }
  },
}
</script>
