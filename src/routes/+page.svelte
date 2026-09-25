<script>

    
    import logoCUL from '$lib/assets/cul.png';
	import Footer from '../lib/components/footer.svelte';
    import { goto } from '$app/navigation';
	
	// Estado del formulario de login
	let email = $state('');
	let password = $state('');
	let recordar = $state(false);
	let cargando = $state(false);
	let mensajeError = $state('');

	function manejarLogin(e) {
		e.preventDefault();
		mensajeError = '';

		if (!email || !password) {
			mensajeError = 'Por favor ingresa tu correo y contraseña.';
			return;
		}

		cargando = true;

		// Simulación de autenticación
		setTimeout(() => {
			cargando = false;
			if (email === 'user@semi.edu.co' && password === '123456') {
				alert('¡Inicio de sesión exitoso!');
			} else {
				mensajeError = 'Credenciales incorrectas. Prueba con user@semi.edu.co / 123456';
			}
             goto('/inicio');
		}, 1000);
	}
</script>



<svelte:head>
	<title>Iniciar Sesión | Gestion de Semilleros</title>
</svelte:head>

<div class="min-vh-100 d-flex flex-column bg-light">
	<div class="row g-0 flex-grow-1">
		
		<!-- PANEL LATERAL IZQ-->
		<div
			class="col-lg-6 d-none d-lg-flex flex-column justify-content-between p-5 text-white"
			style="background-color: #0f3460;"
		>
		<div
            class="bg-white rounded-3 d-flex align-items-center justify-content-center"
            style="width: 60px; height: 60px;"
>
        <img
            src={logoCUL}
            alt="Logo CUL"
            style="width: 48px; height: 48px; object-fit: contain;"
    />
</div>

            <span class="fs-4 fw-bold">Gestion de Semilleros</span>

			<!-- Mensaje central -->
			<div class="my-auto py-5 pe-lg-5">
				<h1 class="display-5 fw-bold mb-3">Plataforma de Gestión de Semilleros</h1>
				<p class="lead text-white-50">
					Accede a tu cuenta para gestionar tus semilleros, registrar actividades y mantener un seguimiento efectivo de tus proyectos académicos.
				</p>
			</div>

			<!-- Pie del panel lateral -->
			<div class="small text-white-50">
				© 2026 Gestion de Semilleros - CUL | Todos los derechos reservados.
			</div>
		</div>

		<!-- PANEL DERECHO (Formulario de Login) -->
		<div class="col-lg-6 d-flex align-items-center justify-content-center p-4 p-sm-5 bg-white">
			<div class="w-100" style="max-width: 420px;">
				
				<!-- Logo en móviles -->
				<div class="d-lg-none text-center mb-4">
                <div class="mb-2">
        <img
                src={logoCUL}
                alt="Logo CUL"
                style="width: 70px; height: 70px; object-fit: contain;"
        />
    </div>

    <h3 class="fw-bold">Gestión de Semilleros</h3>
</div>

				<!-- Título -->
				<div class="mb-4">
					<h3 class="fw-bold mb-1">Iniciar Sesión</h3>
					<p class="text-muted">Ingresa tus credenciales para acceder al sistema</p>
				</div>

				<!-- Alerta de Error -->
				{#if mensajeError}
					<div class="alert alert-danger alert-dismissible fade show small" role="alert">
						<span>⚠️ {mensajeError}</span>
						<button type="button" class="btn-close" onclick={() => (mensajeError = '')} aria-label="Close"></button>
					</div>
				{/if}

				<!-- Formulario -->
				<form onsubmit={manejarLogin}>
					<!-- CORREO -->
					<div class="mb-3">
						<label for="email" class="form-label fw-semibold">Correo Electrónico</label>
						<div class="input-group">
							<span class="input-group-text bg-light text-muted">✉️</span>
							<input
								id="email"
								type="email"
								class="form-control"
								placeholder="usuario@institucion.edu.co"
								bind:value={email}
								required
							/>
						</div>
					</div>

					<!-- CONTRASEÑA -->
					<div class="mb-3">
						<div class="d-flex justify-content-between align-items-center mb-1">
							<label for="password" class="form-label fw-semibold mb-0">Contraseña</label>
							<a href="#olvide" class="small text-decoration-none" style="color: #0f3460;">
								¿Olvidaste tu contraseña?
							</a>
						</div>
						<div class="input-group">
							<span class="input-group-text bg-light text-muted">🔒</span>
							<input
								id="password"
								type="password"
								class="form-control"
								placeholder="••••••••"
								bind:value={password}
								required
							/>
						</div>
					</div>

					<!-- RECORDAR SESIÓN -->
					<div class="form-check mb-4">
						<input
							id="recordar"
							type="checkbox"
							class="form-check-input"
							bind:checked={recordar}
						/>
						<label for="recordar" class="form-check-label text-secondary small">
							Recordar mi sesión en este dispositivo
						</label>
					</div>

					<!-- BOTÓN INGRESAR -->
					<button
						type="submit"
						class="btn w-100 text-white py-2 fw-semibold"
						style="background-color: #0f3460;"
						disabled={cargando}
					>
						{#if cargando}
							<span class="spinner-border spinner-border-sm me-2" role="status" aria-hidden="true"></span>
							Iniciando sesión...
						{:else}
							Ingresar al Sistema
						{/if}
					</button>
				</form>

				<!-- Pie de ayuda -->
				<div class="mt-4 text-center">
					<small class="text-muted">
						¿Problemas para acceder?
						<a href="#soporte" class="text-decoration-none fw-semibold" style="color: #0f3460;">
							Contacta con Soporte Técnico
						</a>
					</small>
				</div>

			</div>
		</div>

	</div>
</div>
