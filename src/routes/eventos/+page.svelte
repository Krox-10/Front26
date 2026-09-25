<script>
    import Navbar from '$lib/components/navbar.svelte';
    import Footer from '$lib/components/footer.svelte';
    import Header from '$lib/components/header.svelte';
    let eventos = [
        {
            nombre: 'Reunión Semillero de Software',
            fecha: '15',
            mes: 'SEP',
            hora: '3:00 PM',
            lugar: 'Sala de investigación'
        },
        {
            nombre: 'Socialización de proyectos',
            fecha: '18',
            mes: 'SEP',
            hora: '10:00 AM',
            lugar: 'Auditorio principal'
        },
        {
            nombre: 'Feria de investigación',
            fecha: '25',
            mes: 'SEP',
            hora: '2:00 PM',
            lugar: 'Bloque académico'
        }
    ];
</script>

<Navbar />

<div class="container py-5">

    <div class="d-flex justify-content-between align-items-center mb-4">

        <div>
            <h1 class="fw-bold titulo">
                Eventos
            </h1>

            <p class="text-secondary">
                Consulta las próximas actividades de investigación.
            </p>
        </div>

        <button class="btn btn-primary">
            <i class="bi bi-plus-lg me-2"></i>
            Nuevo evento
        </button>

    </div>


    <div class="card eventos-card">

        <div class="card-body p-4">

            {#each eventos as evento}

                <div class="evento">

                    <div class="fecha">

                        <strong>
                            {evento.fecha}
                        </strong>

                        <small>
                            {evento.mes}
                        </small>

                    </div>


                    <div class="flex-grow-1">

                        <h5 class="fw-bold mb-1">
                            {evento.nombre}
                        </h5>

                        <p class="text-secondary mb-0">

                            <i class="bi bi-clock me-1"></i>
                            {evento.hora}

                            <span class="mx-2">•</span>

                            <i class="bi bi-geo-alt me-1"></i>
                            {evento.lugar}

                        </p>

                    </div>


                    <button class="btn btn-outline-primary">
                        Ver
                    </button>

                </div>

            {/each}

        </div>

    </div>

</div>


<style>
    .titulo {
        color: #0f3460;
    }

    .eventos-card {
        border: none;
        border-radius: 18px;
        box-shadow: 0 4px 15px rgba(15,52,96,.08);
    }

    .evento {
        display: flex;
        align-items: center;
        gap: 20px;

        padding: 20px 5px;
        border-bottom: 1px solid #edf0f4;
    }

    .evento:last-child {
        border-bottom: none;
    }

    .fecha {
        width: 65px;
        height: 65px;
        border-radius: 12px;

        background: #eaf2fb;
        color: #0f3460;

        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .fecha strong {
        font-size: 1.5rem;
    }

    .fecha small {
        font-weight: 600;
    }
</style>