<script>
    import Navbar from '$lib/components/navbar.svelte';

    let semilleros = [
        {
            nombre: 'Semillero de Software',
            linea: 'Desarrollo de software',
            miembros: 8,
            proyectos: 4,
            estado: 'Activo'
        },
        {
            nombre: 'Semillero de Inteligencia Artificial',
            linea: 'Inteligencia artificial',
            miembros: 6,
            proyectos: 3,
            estado: 'Activo'
        },
        {
            nombre: 'Semillero de Redes',
            linea: 'Redes y telecomunicaciones',
            miembros: 5,
            proyectos: 2,
            estado: 'Activo'
        },
        {
            nombre: 'Semillero de Innovación',
            linea: 'Innovación tecnológica',
            miembros: 5,
            proyectos: 3,
            estado: 'Activo'
        }
    ];
</script>

<Navbar />

<div class="container py-5">

    <div class="d-flex justify-content-between align-items-center mb-4">

        <div>
            <h1 class="fw-bold titulo">
                Semilleros
            </h1>

            <p class="text-secondary">
                Consulta y administra los semilleros de investigación.
            </p>
        </div>

        <button class="btn btn-primary">
            <i class="bi bi-plus-lg me-2"></i>
            Nuevo semillero
        </button>

    </div>


    <div class="row g-4">

        {#each semilleros as semillero}

            <div class="col-12 col-md-6 col-xl-4">

                <div class="card semillero-card h-100">

                    <div class="card-body p-4">

                        <div class="d-flex justify-content-between mb-4">

                            <div class="icono">
                                <i class="bi bi-mortarboard"></i>
                            </div>

                            <span class="badge bg-success-subtle text-success">
                                {semillero.estado}
                            </span>

                        </div>

                        <h4 class="fw-bold">
                            {semillero.nombre}
                        </h4>

                        <p class="text-secondary">
                            {semillero.linea}
                        </p>

                        <hr>

                        <div class="d-flex justify-content-between">

                            <span>
                                <i class="bi bi-people me-1"></i>
                                {semillero.miembros} miembros
                            </span>

                            <span>
                                <i class="bi bi-folder me-1"></i>
                                {semillero.proyectos} proyectos
                            </span>

                        </div>

                        <button class="btn btn-outline-primary w-100 mt-4">
                            Ver semillero
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

    .semillero-card {
        border: none;
        border-radius: 18px;
        box-shadow: 0 4px 15px rgba(15,52,96,.08);
        transition: .2s;
    }

    .semillero-card:hover {
        transform: translateY(-4px);
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
</style>