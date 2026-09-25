<script>
    import Navbar from '$lib/components/navbar.svelte';
    import logo from '$lib/assets/cul.png';
    import { goto } from '$app/navigation';
    import Header from '$lib/components/header.svelte';
    let estadisticas = [
        {
            titulo: 'Miembros',
            numero: 24,
            descripcion: 'Registrados en semilleros',
            icono: 'bi-people'
        },
        {
            titulo: 'Semilleros',
            numero: 6,
            descripcion: 'Semilleros activos',
            icono: 'bi-mortarboard'
        },
        {
            titulo: 'Proyectos',
            numero: 12,
            descripcion: 'Proyectos registrados',
            icono: 'bi-folder2-open'
        },
        {
            titulo: 'Eventos',
            numero: 8,
            descripcion: 'Programados este mes',
            icono: 'bi-calendar-event'
        }
    ];


    let acciones = [
        {
            nombre: 'Ver semilleros',
            icono: 'bi-mortarboard',
            ruta: '/semilleros'
        },
        {
            nombre: 'Ver proyectos',
            icono: 'bi-folder2-open',
            ruta: '/proyectos'
        },
        {
            nombre: 'Ver estudiantes',
            icono: 'bi-people',
            ruta: '/Estudiantes'
        },
        {
            nombre: 'Ver eventos',
            icono: 'bi-calendar-event',
            ruta: '/eventos'
        }
    ];


    let semilleros = [
        {
            nombre: 'Semillero de Software',
            miembros: 8,
            proyectos: 4
        },
        {
            nombre: 'Semillero de Inteligencia Artificial',
            miembros: 6,
            proyectos: 3
        },
        {
            nombre: 'Semillero de Redes',
            miembros: 5,
            proyectos: 2
        }
    ];


    let eventos = [
        {
            nombre: 'Reunión de semillero',
            fecha: '15 Sep',
            hora: '3:00 PM'
        },
        {
            nombre: 'Socialización de proyectos',
            fecha: '18 Sep',
            hora: '10:00 AM'
        },
        {
            nombre: 'Feria de investigación',
            fecha: '25 Sep',
            hora: '2:00 PM'
        }
    ];
</script>


<!--
    IMPORTANTE:
    Esta es la ÚNICA navbar.
-->
<Navbar />


<!-- CONTENIDO PRINCIPAL -->

<div class="container-fluid px-4 py-4">


    <!-- BIENVENIDA -->

    <section class="bienvenida mb-4">

        <div class="bienvenida-contenido">

            <span class="badge-panel">
                Panel principal
            </span>


            <h1>
                ¡Bienvenido a Gestión de Semilleros! 👋
            </h1>


            <p>
                Administra tus semilleros, proyectos, estudiantes
                y actividades desde un solo lugar.
            </p>

        </div>


        <!-- LOGO CUL -->

        <div class="logo-inicio">

            <img
                src={logo}
                alt="Logo CUL"
            />

        </div>

    </section>



    <!-- ESTADÍSTICAS -->

    <div class="row g-4 mb-4">

        {#each estadisticas as estadistica}

            <div class="col-12 col-md-6 col-xl-3">

                <div class="card estadistica-card h-100">

                    <div class="card-body">

                        <div class="d-flex justify-content-between align-items-start">

                            <div>

                                <p class="text-secondary mb-2">
                                    {estadistica.titulo}
                                </p>


                                <h2 class="fw-bold numero">
                                    {estadistica.numero}
                                </h2>


                                <p class="text-secondary mb-0">
                                    {estadistica.descripcion}
                                </p>

                            </div>


                            <div class="estadistica-icono">

                                <i class="bi {estadistica.icono}"></i>

                            </div>

                        </div>

                    </div>

                </div>

            </div>

        {/each}

    </div>



    <!-- ACCIONES RÁPIDAS -->

    <div class="card seccion-card mb-4">

        <div class="card-body p-4">

            <h3 class="fw-bold mb-1">
                Acciones rápidas
            </h3>


            <p class="text-secondary mb-4">
                Accede rápidamente a las funciones principales.
            </p>


            <div class="row g-3">

                {#each acciones as accion}

                    <div class="col-12 col-md-6 col-xl-3">

                        <button
                            class="accion-btn w-100"
                            onclick={() => goto(accion.ruta)}
                        >

                            <i class="bi {accion.icono} fs-4"></i>


                            <span>
                                {accion.nombre}
                            </span>


                            <i class="bi bi-arrow-right ms-auto"></i>

                        </button>

                    </div>

                {/each}

            </div>

        </div>

    </div>



    <!-- PARTE INFERIOR -->

    <div class="row g-4">


        <!-- SEMILLEROS -->

        <div class="col-12 col-lg-7">

            <div class="card seccion-card h-100">

                <div class="card-body p-4">

                    <div class="d-flex justify-content-between align-items-center mb-4">

                        <div>

                            <h3 class="fw-bold mb-1">
                                Semilleros
                            </h3>


                            <p class="text-secondary mb-0">
                                Semilleros registrados
                            </p>

                        </div>


                        <button
                            class="btn btn-outline-primary"
                            onclick={() => goto('/semilleros')}
                        >
                            Ver todos
                        </button>

                    </div>


                    {#each semilleros as semillero}

                        <div class="semillero-item">

                            <div class="semillero-icono">

                                <i class="bi bi-mortarboard"></i>

                            </div>


                            <div class="flex-grow-1">

                                <h6 class="fw-bold mb-1">
                                    {semillero.nombre}
                                </h6>


                                <small class="text-secondary">

                                    {semillero.miembros}
                                    miembros

                                    ·

                                    {semillero.proyectos}
                                    proyectos

                                </small>

                            </div>


                            <i class="bi bi-chevron-right text-secondary"></i>

                        </div>

                    {/each}

                </div>

            </div>

        </div>



        <!-- EVENTOS -->

        <div class="col-12 col-lg-5">

            <div class="card seccion-card h-100">

                <div class="card-body p-4">

                    <div class="d-flex justify-content-between align-items-center mb-4">

                        <div>

                            <h3 class="fw-bold mb-1">
                                Próximos eventos
                            </h3>


                            <p class="text-secondary mb-0">
                                Actividades programadas
                            </p>

                        </div>


                        <button
                            class="btn btn-outline-primary btn-sm"
                            onclick={() => goto('/eventos')}
                        >
                            Ver
                        </button>

                    </div>


                    {#each eventos as evento}

                        <div class="evento-item">

                            <div class="fecha-evento">

                                <strong>
                                    {evento.fecha}
                                </strong>

                            </div>


                            <div>

                                <h6 class="fw-bold mb-1">
                                    {evento.nombre}
                                </h6>


                                <small class="text-secondary">

                                    <i class="bi bi-clock me-1"></i>

                                    {evento.hora}

                                </small>

                            </div>

                        </div>

                    {/each}

                </div>

            </div>

        </div>

    </div>

</div>



<!-- FOOTER -->

<footer class="footer mt-5">

    <div class="container text-center py-4">

        <strong>
            Gestión de Semilleros
        </strong>


        <p class="text-secondary mb-0">
            Plataforma académica de investigación · CUL
        </p>

    </div>

</footer>



<style>

    :global(body) {
        background-color: #f7f9fc;
    }


    .bienvenida {

        min-height: 255px;

        border-radius: 20px;

        padding: 50px;

        color: white;

        background: linear-gradient(
            135deg,
            #0f3460,
            #1f5b91
        );

        display: flex;

        align-items: center;

        justify-content: space-between;

        overflow: hidden;

    }


    .bienvenida-contenido {
        max-width: 900px;
    }


    .badge-panel {

        display: inline-block;

        background-color: rgba(255,255,255,.2);

        padding: 8px 20px;

        border-radius: 7px;

        font-weight: 600;

        font-size: 13px;

        margin-bottom: 20px;

    }


    .bienvenida h1 {

        font-size: 2.5rem;

        font-weight: 700;

        margin-bottom: 12px;

    }


    .bienvenida p {

        font-size: 1.1rem;

        color: #d6e2f0;

        margin-bottom: 0;

    }


    .logo-inicio {

        width: 150px;
        height: 150px;

        background-color: white;

        border-radius: 50%;

        display: flex;

        align-items: center;

        justify-content: center;

        margin-right: 30px;

    }


    .logo-inicio img {

        width: 110px;
        height: 110px;

        object-fit: contain;

    }


    .estadistica-card {

        border: none;

        border-radius: 18px;

        box-shadow:
            0 4px 15px rgba(15,52,96,.08);

    }


    .numero {

        color: #0f3460;

        font-size: 2.2rem;

    }


    .estadistica-icono {

        width: 52px;
        height: 52px;

        border-radius: 12px;

        background-color: #eaf2fb;

        color: #0f3460;

        display: flex;

        align-items: center;

        justify-content: center;

        font-size: 1.4rem;

    }


    .seccion-card {

        border: none;

        border-radius: 18px;

        box-shadow:
            0 4px 15px rgba(15,52,96,.07);

    }


    .accion-btn {

        border: 1px solid #dce3eb;

        background-color: white;

        border-radius: 12px;

        padding: 20px;

        display: flex;

        align-items: center;

        gap: 14px;

        font-weight: 600;

        transition: .2s;

    }


    .accion-btn:hover {

        border-color: #0f3460;

        color: #0f3460;

        transform: translateY(-2px);

        box-shadow:
            0 5px 12px rgba(15,52,96,.08);

    }


    .semillero-item {

        display: flex;

        align-items: center;

        gap: 15px;

        padding: 15px 0;

        border-bottom: 1px solid #edf0f4;

    }


    .semillero-item:last-child {
        border-bottom: none;
    }


    .semillero-icono {

        width: 45px;
        height: 45px;

        border-radius: 10px;

        background-color: #eaf2fb;

        color: #0f3460;

        display: flex;

        align-items: center;

        justify-content: center;

    }


    .evento-item {

        display: flex;

        align-items: center;

        gap: 15px;

        padding: 15px 0;

        border-bottom: 1px solid #edf0f4;

    }


    .evento-item:last-child {
        border-bottom: none;
    }


    .fecha-evento {

        min-width: 70px;

        height: 50px;

        border-radius: 10px;

        background-color: #eaf2fb;

        color: #0f3460;

        display: flex;

        align-items: center;

        justify-content: center;

        text-align: center;

        font-size: 13px;

    }


    .footer {

        background-color: white;

        border-top: 1px solid #e9edf2;

    }


    @media (max-width: 768px) {

        .bienvenida {

            padding: 35px 25px;

        }


        .bienvenida h1 {

            font-size: 1.8rem;

        }


        .logo-inicio {

            display: none;

        }

    }

</style>