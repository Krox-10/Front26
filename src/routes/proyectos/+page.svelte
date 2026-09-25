<script>
    import Navbar from '$lib/components/navbar.svelte';
    

    let proyectos = [
        {
            nombre: 'Sistema de gestión académica',
            semillero: 'Software',
            estado: 'En desarrollo',
            progreso: 75
        },
        {
            nombre: 'Sistema inteligente de residuos',
            semillero: 'Inteligencia Artificial',
            estado: 'En investigación',
            progreso: 50
        },
        {
            nombre: 'Red universitaria inteligente',
            semillero: 'Redes',
            estado: 'Finalizado',
            progreso: 100
        }
    ];
</script>

<Navbar />

<div class="container py-5">

    <div class="mb-4">
        <h1 class="fw-bold titulo">
            Proyectos
        </h1>

        <p class="text-secondary">
            Consulta los proyectos asociados a los semilleros.
        </p>
    </div>


    <div class="row g-4">

        {#each proyectos as proyecto}

            <div class="col-12 col-lg-4">

                <div class="card proyecto-card h-100">

                    <div class="card-body p-4">

                        <div class="icono mb-3">
                            <i class="bi bi-folder2-open"></i>
                        </div>

                        <h4 class="fw-bold">
                            {proyecto.nombre}
                        </h4>

                        <p class="text-secondary">
                            Semillero: {proyecto.semillero}
                        </p>

                        <span class="badge bg-primary-subtle text-primary">
                            {proyecto.estado}
                        </span>

                        <div class="mt-4">

                            <div class="d-flex justify-content-between mb-2">
                                <small>Progreso</small>
                                <small>{proyecto.progreso}%</small>
                            </div>

                            <div class="progress">
                                <div
                                    class="progress-bar"
                                    style={`width: ${proyecto.progreso}%`}
                                ></div>
                            </div>

                        </div>

                        <button class="btn btn-outline-primary w-100 mt-4">
                            Ver proyecto
                        </button>

                    </div>

                </div>

            </div>

        {/each}

    </div>

</div>


<style>
    .titulo {
        color: #0f3460;
    }

    .proyecto-card {
        border: none;
        border-radius: 18px;
        box-shadow: 0 4px 15px rgba(15,52,96,.08);
    }

    .icono {
        width: 52px;
        height: 52px;
        border-radius: 12px;

        background: #eaf2fb;
        color: #0f3460;

        display: flex;
        align-items: center;
        justify-content: center;

        font-size: 1.4rem;
    }

    .progress {
        height: 8px;
        border-radius: 10px;
    }
</style>