# Gustavo-Portilla-M-ndez
STEAM Project - My OWN Page

<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Savia | Psicología y Ciencias Humanas</title>

  <style>
    /* ===== CONFIGURACIÓN GENERAL ===== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: var(--fondo);
      color: var(--texto);
      line-height: 1.65;
      transition: background 0.2s, color 0.2s;
    }

    :root {
      --verde: #203d2f;
      --verde-hover: #2f5241;
      --verde-claro: #d9e4dc;
      --verde-suave: #edf1ec;
      --fondo: #f7f8f4;
      --blanco: #ffffff;
      --texto: #243e31;
      --gris: #68756d;
      --borde: #e1e6df;
    }

    /* MODO ALTO CONTRASTE (ACCESIBILIDAD) */
    body.alto-contraste {
      --verde: #000000;
      --verde-hover: #222222;
      --verde-claro: #e6ebe7;
      --verde-suave: #f0f0f0;
      --fondo: #ffffff;
      --blanco: #ffffff;
      --texto: #000000;
      --gris: #222222;
      --borde: #000000;
    }

    body.alto-contraste a:focus,
    body.alto-contraste button:focus,
    body.alto-contraste input:focus,
    body.alto-contraste select:focus,
    body.alto-contraste textarea:focus {
      outline: 3px solid #000000;
      outline-offset: 2px;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    button {
      font-family: inherit;
      cursor: pointer;
    }

    .contenedor {
      width: 90%;
      max-width: 1180px;
      margin: auto;
    }

    .etiqueta {
      font-size: 10px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: #627851;
      font-weight: bold;
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    body.alto-contraste .etiqueta {
      color: #000000;
    }

    .punto-etiqueta {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: #627851;
      display: inline-block;
    }

    h1, h2, h3 {
      font-family: Georgia, 'Times New Roman', serif;
      font-weight: normal;
      line-height: 1.14;
    }

    h1 {
      font-size: clamp(38px, 5vw, 62px);
      letter-spacing: -1.5px;
    }

    h2 {
      font-size: clamp(28px, 3.8vw, 42px);
      letter-spacing: -1px;
    }

    .descripcion {
      font-size: 14px;
      color: var(--gris);
      max-width: 640px;
      margin-top: 16px;
    }

    .nota-pie-seccion {
      font-size: 10px;
      color: var(--gris);
      margin-top: 22px;
    }

    /* BREADCRUMB */
    .breadcrumb {
      font-size: 11px;
      color: var(--gris);
      margin-bottom: 24px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .breadcrumb a:hover {
      text-decoration: underline;
    }

    /* AVISO DESTACADO */
    .banner-aviso {
      background: var(--verde-claro);
      border-radius: 8px;
      padding: 20px 24px;
      margin: 28px 0 36px;
    }

    .banner-aviso strong {
      display: block;
      font-size: 12px;
      margin-bottom: 5px;
    }

    .banner-aviso p {
      font-size: 11.5px;
      color: var(--texto);
      opacity: 0.85;
    }

    /* ===== CONTROL DE VISTAS (PÁGINAS) ===== */
    .vista {
      display: none;
      animation: aparecer 0.25s ease;
    }

    .vista.activa {
      display: block;
    }

    @keyframes aparecer {
      from { opacity: 0; transform: translateY(4px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* ===== ENCABEZADO ===== */
    header {
      background: var(--fondo);
      border-bottom: 1px solid var(--borde);
      padding: 18px 0;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .barra {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 12px;
      cursor: pointer;
    }

    .logo-icono {
      width: 38px;
      height: 38px;
      flex-shrink: 0;
    }

    .logo-texto {
      font-family: Georgia, serif;
      font-size: 26px;
      letter-spacing: -0.5px;
      line-height: 1;
    }

    .logo-texto small {
      display: block;
      font-family: Arial, sans-serif;
      font-size: 8.5px;
      letter-spacing: 1.8px;
      text-transform: uppercase;
      color: var(--gris);
      margin-top: 4px;
    }

    nav {
      display: flex;
      align-items: center;
      gap: 22px;
      font-size: 12.5px;
    }

    nav a {
      padding: 6px 0;
      border-bottom: 2px solid transparent;
      color: var(--texto);
      transition: 0.2s;
    }

    nav a:hover {
      color: #627851;
    }

    nav a.nav-activo {
      border-bottom-color: var(--verde);
      font-weight: bold;
    }

    .btn-nav {
      background: var(--verde);
      color: white !important;
      padding: 11px 20px !important;
      border-radius: 6px;
      font-size: 12px;
      border-bottom: none !important;
      transition: 0.2s;
    }

    .btn-nav:hover {
      background: var(--verde-hover);
    }

    /* ===== BOTONES GENERALES ===== */
    .boton {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      background: var(--verde);
      color: white;
      padding: 13px 22px;
      border-radius: 6px;
      font-size: 12.5px;
      border: 1px solid var(--verde);
      transition: 0.25s;
    }

    .boton:hover {
      background: var(--verde-hover);
      transform: translateY(-1px);
    }

    .boton-outline {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      background: transparent;
      color: var(--texto);
      padding: 12px 20px;
      border-radius: 6px;
      font-size: 12.5px;
      border: 1px solid var(--texto);
      transition: 0.2s;
    }

    .boton-outline:hover {
      background: rgba(32, 61, 47, 0.06);
    }

    .enlace-flecha {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-size: 12.5px;
      font-weight: bold;
      color: var(--verde);
      border-bottom: 1px solid transparent;
      padding-bottom: 2px;
      transition: 0.2s;
    }

    .enlace-flecha:hover {
      border-bottom-color: var(--verde);
    }

    /* ===== SECCIÓN HERO ===== */
    .hero {
      padding: 60px 0 50px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.05fr 0.95fr;
      align-items: center;
      gap: 60px;
    }

    .hero-descripcion {
      color: var(--gris);
      font-size: 14.5px;
      max-width: 470px;
      margin-top: 20px;
    }

    .hero-acciones {
      display: flex;
      align-items: center;
      gap: 24px;
      margin-top: 28px;
      flex-wrap: wrap;
    }

    .hero-nota-icono {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 11px;
      color: var(--gris);
      margin-top: 22px;
    }

    .pill-acreditacion {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: var(--verde-suave);
      border: 1px solid var(--borde);
      padding: 7px 14px;
      border-radius: 20px;
      font-size: 11px;
      font-weight: bold;
      color: var(--texto);
      margin-top: 22px;
    }

    .imagen-arco-wrap {
      position: relative;
    }

    .imagen-arco {
      width: 100%;
      height: 460px;
      object-fit: cover;
      border-top-left-radius: 150px;
      border-top-right-radius: 12px;
      border-bottom-left-radius: 12px;
      border-bottom-right-radius: 12px;
      display: block;
    }

    .tarjeta-flotante {
      position: absolute;
      bottom: 18px;
      left: 18px;
      right: 18px;
      background: rgba(255, 255, 255, 0.96);
      padding: 16px 20px;
      border-radius: 8px;
      display: flex;
      align-items: center;
      gap: 14px;
      box-shadow: 0 8px 24px rgba(0,0,0,0.06);
      color: #243e31;
    }

    .tarjeta-flotante strong {
      font-family: Georgia, serif;
      font-weight: normal;
      font-size: 15px;
      display: block;
    }

    .tarjeta-flotante span {
      font-size: 11px;
      color: #68756d;
    }

    .pie-foto {
      font-size: 10.5px;
      color: var(--gris);
      margin-top: 10px;
    }

    /* ===== FRANJA DE PUNTOS CLAVE ===== */
    .franja-conecta {
      border-top: 1px solid var(--borde);
      border-bottom: 1px solid var(--borde);
      padding: 22px 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 20px;
    }

    .franja-conecta .etiqueta {
      margin-bottom: 0;
    }

    .franja-items {
      display: flex;
      gap: 36px;
      flex-wrap: wrap;
      font-family: Georgia, serif;
      font-size: 15px;
    }

    .franja-items span::before {
      content: "• ";
      color: #627851;
    }

    /* ===== DATOS DEL PROGRAMA ===== */
    .datos-programa {
      border-top: 1px solid var(--borde);
      border-bottom: 1px solid var(--borde);
      padding: 26px 0;
      margin-top: 35px;
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
    }

    .dato-item small {
      display: block;
      font-size: 10.5px;
      color: var(--gris);
      margin-bottom: 4px;
    }

    .dato-item strong {
      font-family: Georgia, serif;
      font-weight: normal;
      font-size: 20px;
    }

    /* ===== SECCIÓN OSCURA ===== */
    .seccion-oscura {
      background: var(--verde);
      color: white;
      padding: 85px 0;
    }

    .seccion-oscura .etiqueta {
      color: #b8ccb9;
    }

    .grid-oscuro-2col {
      display: grid;
      grid-template-columns: 0.85fr 1.15fr;
      gap: 70px;
      align-items: start;
    }

    .texto-claro {
      color: #cad7cc;
      font-size: 13.5px;
      margin-top: 18px;
    }

    .linea-corta {
      width: 45px;
      height: 1px;
      background: rgba(255,255,255,0.3);
      margin-top: 28px;
    }

    .pilares-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 35px 40px;
    }

    .pilar-icono {
      width: 24px;
      height: 24px;
      margin-bottom: 12px;
      color: #b8d0bb;
    }

    .pilar h3 {
      font-size: 19px;
      margin-bottom: 8px;
    }

    .pilar p {
      font-size: 12.5px;
      color: #c5d3c8;
    }

    .habilidades-lista {
      display: grid;
      gap: 26px;
    }

    .habilidad-item {
      display: flex;
      gap: 16px;
      align-items: flex-start;
    }

    .icono-check-circulo {
      width: 20px;
      height: 20px;
      border: 1px solid #b8d0bb;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 11px;
      color: #b8d0bb;
      flex-shrink: 0;
      margin-top: 3px;
    }

    .habilidad-item h3 {
      font-size: 19px;
    }

    .habilidad-item p {
      font-size: 12.5px;
      color: #c5d3c8;
      margin-top: 5px;
    }

    .tarjeta-blanca-oscura {
      background: var(--fondo);
      color: var(--texto);
      padding: 34px;
      border-radius: 10px;
    }

    .tarjeta-blanca-oscura h3 {
      font-size: 22px;
      margin-bottom: 14px;
    }

    .tarjeta-blanca-oscura ul {
      list-style: none;
      font-size: 13px;
      color: var(--gris);
      margin-bottom: 20px;
    }

    .tarjeta-blanca-oscura li {
      margin-bottom: 5px;
    }

    /* ===== TARJETAS DE ÁREAS / ESPECIALIDADES ===== */
    .seccion-clara {
      padding: 65px 0 80px;
    }

    .encabezado-doble {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      gap: 30px;
      margin-bottom: 35px;
    }

    .encabezado-doble-lado {
      max-width: 360px;
    }

    .encabezado-doble-lado p {
      font-size: 13px;
      color: var(--gris);
      margin-bottom: 12px;
    }

    .areas-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
    }

    .tarjeta-area {
      background: white;
      border: 1px solid var(--borde);
      border-radius: 10px;
      padding: 24px;
      transition: 0.2s;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .tarjeta-area:hover {
      border-color: #9aaf9b;
      transform: translateY(-2px);
    }

    .tarjeta-area-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 18px;
    }

    .caja-icono {
      width: 34px;
      height: 34px;
      background: var(--verde-suave);
      border-radius: 6px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--verde);
      flex-shrink: 0;
    }

    .flecha-card {
      color: var(--gris);
      font-size: 14px;
    }

    .sub-etiqueta {
      font-size: 9px;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      color: #627851;
      font-weight: bold;
      margin-bottom: 6px;
    }

    .tarjeta-area h3 {
      font-size: 21px;
      margin-bottom: 8px;
    }

    .tarjeta-area p {
      font-size: 12.5px;
      color: var(--gris);
    }

    .tarjeta-area-compacta {
      background: white;
      border: 1px solid var(--borde);
      border-radius: 8px;
      padding: 22px;
    }

    .tarjeta-area-compacta-titulo {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 8px;
    }

    .tarjeta-area-compacta h3 {
      font-size: 20px;
    }

    .tarjeta-area-compacta p {
      font-size: 12px;
      color: var(--gris);
      padding-left: 32px;
    }

    /* ===== VISTA PREVIA TAREA 5: MI RUTA VOCACIONAL (SUPABASE AUTH) ===== */
    .seccion-preview-funcion {
      background: var(--verde-suave);
      border-top: 1px solid var(--borde);
      border-bottom: 1px solid var(--borde);
      padding: 75px 0;
    }

    .badge-desarrollo {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: #203d2f;
      color: #ffffff;
      font-size: 10px;
      font-weight: bold;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      padding: 6px 14px;
      border-radius: 20px;
      margin-bottom: 16px;
    }

    .badge-desarrollo::before {
      content: "";
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #a8d5ba;
    }

    .preview-grid {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 32px;
      margin-top: 32px;
      align-items: start;
    }

    .preview-card {
      background: white;
      border: 1px solid var(--borde);
      border-radius: 12px;
      padding: 28px;
    }

    .preview-card.dashed {
      border: 1.5px dashed #8fa393;
      background: #fcfdfb;
    }

    .auth-mockup-bar {
      background: var(--verde-suave);
      border: 1px solid var(--borde);
      border-radius: 8px;
      padding: 12px 16px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      margin-bottom: 20px;
      flex-wrap: wrap;
      font-size: 12px;
    }

    .chips-especialidad {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 6px;
    }

    .chip-esp {
      background: white;
      border: 1px solid var(--borde);
      padding: 7px 13px;
      border-radius: 20px;
      font-size: 12px;
      color: var(--texto);
      transition: 0.2s;
    }

    .chip-esp:hover {
      border-color: var(--verde);
    }

    .chip-esp.activo {
      background: var(--verde);
      color: white;
      border-color: var(--verde);
      font-weight: bold;
    }

    .resumen-guardado-box {
      background: var(--verde-suave);
      border-radius: 8px;
      padding: 18px;
      margin-top: 16px;
      border-left: 3px solid var(--verde);
    }

    .aviso-no-persiste {
      margin-top: 16px;
      padding: 10px 14px;
      background: #f3f5f0;
      border-radius: 6px;
      font-size: 11px;
      color: var(--gris);
    }

    /* ===== ACORDEÓN (SEMESTRES Y PREGUNTAS FRECUENTES) ===== */
    .recorrido-grid {
      display: grid;
      grid-template-columns: 1.35fr 0.65fr;
      gap: 30px;
      align-items: start;
    }

    .acordeon-lista {
      display: grid;
      gap: 12px;
    }

    .acordeon-item {
      background: white;
      border: 1px solid var(--borde);
      border-radius: 8px;
      overflow: hidden;
    }

    .acordeon-header {
      width: 100%;
      background: white;
      border: none;
      padding: 18px 22px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
      text-align: left;
      color: var(--texto);
    }

    .acordeon-header:hover {
      background: #fafbf8;
    }

    .semestre-num {
      font-size: 10px;
      color: #627851;
      font-weight: bold;
      display: block;
      margin-bottom: 3px;
    }

    .acordeon-titulo {
      font-size: 14px;
      font-weight: bold;
    }

    .acordeon-signo {
      font-size: 20px;
      color: var(--gris);
      font-weight: normal;
      flex-shrink: 0;
    }

    .acordeon-body {
      display: none;
      padding: 14px 22px 20px;
      border-top: 1px solid var(--borde);
      font-size: 12.5px;
      color: var(--gris);
    }

    .acordeon-item.abierto .acordeon-body {
      display: block;
    }

    .materias-lista {
      list-style: none;
      display: grid;
      gap: 8px;
    }

    .materias-lista li {
      font-size: 12.5px;
      color: var(--gris);
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .semestre-meta {
      font-size: 10.5px;
      color: var(--gris);
      margin-top: 14px;
    }

    /* ===== FAQ ESPECÍFICO ===== */
    .faq-tabs {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin: 26px 0 12px;
    }

    .faq-tab {
      background: white;
      border: 1px solid var(--borde);
      padding: 9px 16px;
      border-radius: 6px;
      font-size: 12px;
      color: var(--texto);
      transition: 0.2s;
    }

    .faq-tab:hover {
      border-color: var(--verde);
    }

    .faq-tab.activa {
      background: var(--verde);
      color: white;
      border-color: var(--verde);
      font-weight: bold;
    }

    .faq-bloque {
      display: grid;
      grid-template-columns: 0.55fr 1.45fr;
      gap: 40px;
      padding: 36px 0;
      border-top: 1px solid var(--borde);
      align-items: start;
    }

    .faq-bloque h3 {
      font-size: 24px;
      margin-bottom: 8px;
    }

    .faq-bloque > div > p {
      font-size: 12px;
      color: var(--gris);
    }

    /* ===== TARJETAS LATERALES ===== */
    .sidebar-cards {
      display: grid;
      gap: 20px;
    }

    .card-verde-suave {
      background: var(--verde-claro);
      border-radius: 10px;
      padding: 26px;
    }

    .card-verde-suave h3 {
      font-size: 23px;
      margin: 12px 0;
    }

    .card-verde-suave p {
      font-size: 12.5px;
      color: var(--texto);
      opacity: 0.85;
      margin-bottom: 14px;
    }

    .card-blanca-borde {
      background: white;
      border: 1px solid var(--borde);
      border-radius: 10px;
      padding: 26px;
    }

    .card-blanca-borde h3 {
      font-size: 21px;
      margin-bottom: 12px;
    }

    .tabla-costos {
      width: 100%;
      font-size: 12.5px;
      margin: 14px 0;
      border-collapse: collapse;
    }

    .tabla-costos td {
      padding: 6px 0;
      color: var(--gris);
    }

    .tabla-costos td:last-child {
      text-align: right;
      font-weight: bold;
      color: var(--texto);
    }

    .tabla-costos tr.total td {
      border-top: 1px solid var(--borde);
      padding-top: 10px;
      color: var(--texto);
    }

    /* ===== DOCENTES ===== */
    .seccion-verde-claro {
      background: var(--verde-claro);
      padding: 75px 0;
    }

    .tarjetas-docentes {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .docente {
      background: white;
      border-radius: 10px;
      padding: 22px;
    }

    .docente-persona {
      display: flex;
      align-items: center;
      gap: 15px;
      margin-bottom: 14px;
    }

    .docente img {
      width: 72px;
      height: 72px;
      object-fit: cover;
      border-radius: 8px;
    }

    .docente h3 {
      font-size: 19px;
    }

    .docente .especialidad {
      color: var(--gris);
      font-size: 11px;
      margin-top: 2px;
    }

    .docente > p {
      color: var(--gris);
      font-size: 12px;
    }

    /* ===== FORMULARIOS ===== */
    .pasos-barra {
      background: var(--verde-suave);
      border: 1px solid var(--borde);
      border-radius: 8px;
      padding: 14px 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 28px 0 12px;
      flex-wrap: wrap;
      gap: 15px;
    }

    .paso-pill {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 12px;
      color: var(--gris);
    }

    .paso-pill.activo {
      color: var(--texto);
      font-weight: bold;
    }

    .paso-num {
      width: 24px;
      height: 24px;
      border-radius: 50%;
      border: 1px solid var(--gris);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 11px;
    }

    .paso-pill.activo .paso-num {
      background: var(--verde);
      color: white;
      border-color: var(--verde);
    }

    .admisiones-grid {
      display: grid;
      grid-template-columns: 1.35fr 0.65fr;
      gap: 30px;
      margin-top: 25px;
      align-items: start;
    }

    .dos-col-equilibrado {
      display: grid;
      grid-template-columns: 0.95fr 1.05fr;
      gap: 50px;
      align-items: start;
    }

    .formulario-caja {
      background: white;
      border: 1px solid var(--borde);
      border-radius: 10px;
      padding: 32px;
    }

    .form-bloque {
      padding-bottom: 26px;
      margin-bottom: 26px;
      border-bottom: 1px solid var(--borde);
    }

    .form-bloque-titulo {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 18px;
    }

    .badge-num {
      width: 24px;
      height: 24px;
      border-radius: 50%;
      background: var(--verde-claro);
      color: var(--verde);
      font-size: 11px;
      font-weight: bold;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .form-bloque-titulo h3 {
      font-size: 20px;
    }

    .campo {
      margin-bottom: 16px;
    }

    .campo label {
      display: block;
      font-size: 11.5px;
      font-weight: bold;
      margin-bottom: 6px;
    }

    .campo input, .campo select, .campo textarea {
      width: 100%;
      padding: 11px 14px;
      border: 1px solid var(--borde);
      border-radius: 6px;
      font-size: 13px;
      font-family: inherit;
      color: var(--texto);
      background: white;
    }

    .campo textarea {
      min-height: 95px;
      resize: vertical;
    }

    .campo input:focus, .campo select:focus, .campo textarea:focus {
      outline: none;
      border-color: var(--verde);
    }

    .campo small {
      display: block;
      font-size: 10.5px;
      color: var(--gris);
      margin-top: 5px;
    }

    .fila-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
    }

    .horario-opciones {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }

    .btn-horario {
      background: white;
      border: 1px solid var(--borde);
      padding: 10px;
      border-radius: 6px;
      font-size: 12px;
      color: var(--texto);
      transition: 0.2s;
    }

    .btn-horario.seleccionado {
      background: var(--verde-claro);
      border-color: var(--verde);
      font-weight: bold;
    }

    .zona-archivo {
      border: 1.5px dashed #b7c4b9;
      border-radius: 8px;
      padding: 28px 20px;
      text-align: center;
      margin-top: 14px;
    }

    .zona-archivo strong {
      display: block;
      font-size: 12.5px;
      margin-top: 8px;
    }

    .zona-archivo span {
      display: block;
      font-size: 10.5px;
      color: var(--gris);
      margin: 4px 0 14px;
    }

    .btn-secundario {
      background: white;
      border: 1px solid var(--texto);
      padding: 9px 18px;
      border-radius: 6px;
      font-size: 12px;
      color: var(--texto);
    }

    .archivo-adjunto {
      background: var(--verde-suave);
      border-radius: 6px;
      padding: 12px 16px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 12px;
      font-size: 12px;
    }

    .checkbox-privacidad {
      display: flex;
      align-items: flex-start;
      gap: 10px;
      font-size: 12px;
      margin-bottom: 10px;
    }

    .checkbox-privacidad input {
      margin-top: 3px;
      accent-color: var(--verde);
    }

    .envio-fila {
      display: flex;
      align-items: center;
      gap: 18px;
      margin-top: 20px;
      flex-wrap: wrap;
    }

    .mensaje-exito {
      display: none;
      background: var(--verde-claro);
      color: var(--verde);
      padding: 14px 18px;
      border-radius: 6px;
      font-size: 12.5px;
      margin-top: 16px;
    }

    /* ===== DOCUMENTO DE PRIVACIDAD ===== */
    .legal-grid {
      display: grid;
      grid-template-columns: 0.65fr 1.35fr;
      gap: 55px;
      align-items: start;
      margin-top: 35px;
    }

    .indice-legal {
      position: sticky;
      top: 95px;
    }

    .indice-legal a {
      display: block;
      font-size: 12px;
      color: var(--gris);
      padding: 6px 0;
    }

    .indice-legal a:hover {
      color: var(--verde);
      font-weight: bold;
    }

    .bloque-legal {
      margin-bottom: 38px;
    }

    .bloque-legal h2 {
      font-size: 24px;
      margin-bottom: 14px;
    }

    .bloque-legal p {
      font-size: 13.5px;
      color: var(--gris);
      margin-bottom: 14px;
    }

    .caja-cookies {
      background: white;
      border: 1px solid var(--borde);
      border-radius: 10px;
      padding: 24px;
      margin-top: 18px;
    }

    .cookie-fila {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 6px;
      font-size: 13px;
    }

    /* ===== ACCESIBILIDAD ===== */
    .selector-contraste {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
      margin: 20px 0 16px;
    }

    .card-contraste {
      border: 1.5px solid var(--borde);
      border-radius: 8px;
      padding: 18px;
      text-align: left;
      transition: 0.2s;
    }

    .card-contraste.estandar {
      background: #f7f8f4;
      color: #243e31;
    }

    .card-contraste.alto {
      background: #203d2f;
      color: #ffffff;
      border-color: #203d2f;
    }

    .card-contraste .aa {
      font-family: Georgia, serif;
      font-size: 24px;
      display: block;
      margin-bottom: 10px;
    }

    .card-contraste span {
      font-size: 11.5px;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .teclas-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 22px;
      margin: 28px 0;
    }

    .tecla-badge {
      display: inline-block;
      border: 1px solid var(--texto);
      border-radius: 6px;
      padding: 6px 14px;
      font-size: 12px;
      font-weight: bold;
      background: white;
      color: var(--texto);
      margin-bottom: 10px;
    }

    .foco-ejemplo-fila {
      display: flex;
      align-items: center;
      gap: 24px;
      padding: 20px 0 32px;
      border-bottom: 1px solid var(--borde);
      margin-bottom: 36px;
      flex-wrap: wrap;
    }

    .btn-foco-demo {
      background: white;
      border: 2px solid var(--verde);
      box-shadow: 0 0 0 3px rgba(32, 61, 47, 0.2);
      padding: 12px 20px;
      border-radius: 8px;
      font-size: 12.5px;
      font-weight: bold;
      color: var(--texto);
    }

    /* ===== CTA FINAL ===== */
    .cta-final {
      background: var(--verde-claro);
      padding: 75px 0;
    }

    .cta-grid {
      display: grid;
      grid-template-columns: 1.3fr 0.7fr;
      align-items: center;
      gap: 40px;
    }

    .cta-grid p {
      color: var(--texto);
      opacity: 0.85;
      font-size: 13.5px;
      margin-top: 14px;
      max-width: 560px;
    }

    .cta-derecha {
      text-align: center;
    }

    .cta-derecha small {
      display: block;
      margin-top: 10px;
      font-size: 11px;
      color: var(--texto);
    }

    /* ===== PIE DE PÁGINA ===== */
    footer {
      background: var(--fondo);
      padding: 55px 0 25px;
      border-top: 1px solid var(--borde);
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 1.3fr 0.8fr 1fr 0.9fr;
      gap: 35px;
      padding-bottom: 40px;
    }

    footer h4 {
      font-size: 11.5px;
      margin-bottom: 12px;
      color: var(--texto);
    }

    footer p, footer a {
      font-size: 11.5px;
      color: var(--gris);
    }

    footer a {
      display: block;
      margin: 6px 0;
    }

    footer a:hover {
      color: var(--verde);
    }

    .footer-final {
      border-top: 1px solid var(--borde);
      padding-top: 20px;
      display: flex;
      justify-content: space-between;
      font-size: 10.5px;
      color: var(--gris);
    }

    .footer-links-legal {
      display: flex;
      gap: 20px;
    }

    .footer-links-legal a {
      margin: 0;
      font-size: 10.5px;
    }

    /* ===== RESPONSIVE ===== */
    @media (max-width: 900px) {
      .hero-grid,
      .grid-oscuro-2col,
      .recorrido-grid,
      .admisiones-grid,
      .dos-col-equilibrado,
      .legal-grid,
      .faq-bloque,
      .preview-grid,
      .cta-grid {
        grid-template-columns: 1fr;
        gap: 32px;
      }

      .indice-legal {
        position: static;
      }

      .areas-grid,
      .tarjetas-docentes,
      .teclas-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .datos-programa {
        grid-template-columns: repeat(2, 1fr);
      }

      .footer-grid {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    @media (max-width: 600px) {
      .barra {
        flex-direction: column;
        align-items: flex-start;
      }

      nav {
        flex-wrap: wrap;
        gap: 14px;
      }

      .areas-grid,
      .tarjetas-docentes,
      .pilares-grid,
      .fila-2,
      .horario-opciones,
      .selector-contraste,
      .teclas-grid,
      .datos-programa,
      .footer-grid {
        grid-template-columns: 1fr;
      }

      .imagen-arco {
        height: 320px;
      }

      .cta-derecha {
        text-align: left;
      }

      .footer-final {
        flex-direction: column;
        gap: 10px;
      }
    }
  </style>
</head>

<body>

  <!-- ENCABEZADO Y MENÚ -->
  <header>
    <div class="contenedor barra">
      <a href="#inicio" class="logo" onclick="mostrarVista('inicio', event)">
        <svg class="logo-icono" viewBox="0 0 40 40" fill="none">
          <circle cx="20" cy="20" r="18.5" stroke="currentColor" stroke-width="1.2"/>
          <path d="M18 19C14.5 19 12 16.5 12 13.5C15.5 13.5 18 15.5 18 19Z" stroke="currentColor" stroke-width="1.2"/>
          <path d="M21 21C24.5 21 28 18 28 14C24 14 21 16.5 21 21Z" stroke="currentColor" stroke-width="1.2"/>
        </svg>
        <div class="logo-texto">
          savia
          <small>Psicología y ciencias humanas</small>
        </div>
      </a>

      <nav>
        <a href="#inicio" id="nav-inicio" class="nav-activo" onclick="mostrarVista('inicio', event)">Inicio</a>
        <a href="#programa" id="nav-programa" onclick="mostrarVista('programa', event)">Conoce el programa</a>
        <a href="#especialidades" id="nav-especialidades" onclick="mostrarVista('especialidades', event)">Especialidades</a>
        <a href="#nosotros" id="nav-nosotros" onclick="mostrarVista('nosotros', event)">Nosotros</a>
        <a href="#mi-ruta-preview" onclick="irAMiRuta(event)">Mi ruta</a>
        <a href="#inscribirme" id="nav-inscribirme" class="btn-nav" onclick="mostrarVista('inscribirme', event)">Inscribirme</a>
      </nav>
    </div>
  </header>

  <!-- =========================================================
       VISTA 1: INICIO
       ========================================================= -->
  <main id="vista-inicio" class="vista activa">
    <section class="hero">
      <div class="contenedor hero-grid">
        <div>
          <p class="etiqueta"><span class="punto-etiqueta"></span> Formación con sentido humano</p>
          <h1>Entender mentes.<br>Cambiar vidas.</h1>
          <p class="hero-descripcion">
            Fórmate en psicología y ciencias de la salud mental. Integra conocimiento científico,
            escucha y sensibilidad para acompañar a las personas en cada etapa de su vida.
          </p>

          <div class="hero-acciones">
            <a href="#inscribirme" class="boton" onclick="mostrarVista('inscribirme', event)">Inscribirme ↗</a>
            <a href="#programa" class="enlace-flecha" onclick="mostrarVista('programa', event)">Conoce el programa ↗</a>
          </div>

          <p class="hero-nota-icono">
            <span>📖</span> Ciencia, ética y compromiso con el bienestar.
          </p>
        </div>

        <div class="imagen-arco-wrap">
          <img class="imagen-arco"
               src="https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?auto=format&fit=crop&w=900&q=80"
               alt="Sesión de acompañamiento y diálogo">
          <div class="tarjeta-flotante">
            <span>💬</span>
            <div>
              <strong>Toda transformación empieza al escuchar.</strong>
              <span>Aprende a mirar más allá de lo evidente.</span>
            </div>
          </div>
        </div>
      </div>

      <div class="contenedor" style="margin-top: 50px;">
        <div class="franja-conecta">
          <p class="etiqueta">Una formación que conecta</p>
          <div class="franja-items">
            <span>La ciencia con la práctica</span>
            <span>La persona con su contexto</span>
            <span>La vocación con el propósito</span>
          </div>
        </div>
      </div>
    </section>

    <section class="seccion-clara" style="padding-top: 40px;">
      <div class="contenedor">
        <div class="encabezado-doble">
          <div>
            <p class="etiqueta">Un campo, muchas formas de acompañar</p>
            <h2>Encuentra tu lugar en la<br>psicología.</h2>
          </div>
          <div class="encabezado-doble-lado">
            <p>
              Descubre seis áreas de estudio para orientar tu vocación y comprender la diversidad
              de la experiencia humana.
            </p>
            <a href="#especialidades" class="enlace-flecha" onclick="mostrarVista('especialidades', event)">
              Explorar especialidades ↗
            </a>
          </div>
        </div>

        <div class="areas-grid">
          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top">
                <div class="caja-icono">♡</div>
                <span class="flecha-card">↗</span>
              </div>
              <p class="sub-etiqueta">Salud y bienestar</p>
              <h3>Clínica</h3>
              <p>Comprende los procesos emocionales y las bases de la evaluación y el acompañamiento psicológico.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top">
                <div class="caja-icono">📖</div>
                <span class="flecha-card">↗</span>
              </div>
              <p class="sub-etiqueta">Aprendizaje y desarrollo</p>
              <h3>Educativa</h3>
              <p>Explora cómo aprendemos y cómo crear entornos educativos inclusivos en las distintas etapas de la vida.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top">
                <div class="caja-icono">⌘</div>
                <span class="flecha-card">↗</span>
              </div>
              <p class="sub-etiqueta">Personas y trabajo</p>
              <h3>Organizacional</h3>
              <p>Promueve el bienestar laboral, el desarrollo del talento y relaciones más saludables en las organizaciones.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top">
                <div class="caja-icono">○</div>
                <span class="flecha-card">↗</span>
              </div>
              <p class="sub-etiqueta">Comunidad y cambio</p>
              <h3>Social</h3>
              <p>Analiza los vínculos entre las personas y su entorno para impulsar la participación y el bienestar colectivo.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top">
                <div class="caja-icono">🧠</div>
                <span class="flecha-card">↗</span>
              </div>
              <p class="sub-etiqueta">Cerebro y conducta</p>
              <h3>Neuropsicología</h3>
              <p>Acércate a la relación entre cerebro, cognición y comportamiento desde una perspectiva interdisciplinaria.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top">
                <div class="caja-icono">🌿</div>
                <span class="flecha-card">↗</span>
              </div>
              <p class="sub-etiqueta">Ciclo vital y vínculos</p>
              <h3>Del desarrollo</h3>
              <p>Estudia los cambios cognitivos, afectivos y sociales desde la infancia hasta el envejecimiento.</p>
            </div>
          </article>
        </div>

        <p class="nota-pie-seccion" style="text-align: center;">
          Cada área abre una perspectiva. La formación de base las conecta con una mirada integral de la persona.
        </p>
      </div>
    </section>

    <section class="seccion-oscura">
      <div class="contenedor grid-oscuro-2col">
        <div>
          <p class="etiqueta">Lo que da sentido a tu formación</p>
          <h2>La ciencia nos guía.<br>La humanidad nos mueve.</h2>
          <p class="texto-claro">
            Prepararte para acompañar a otros requiere más que conocimientos.
            Requiere aprender a observar, cuestionar y actuar con responsabilidad.
          </p>
          <div class="linea-corta"></div>
        </div>

        <div class="pilares-grid">
          <div class="pilar">
            <div class="pilar-icono">🔬</div>
            <h3>Rigor científico</h3>
            <p>Aprende a leer la evidencia, formular preguntas y comprender los fundamentos de la conducta humana.</p>
          </div>

          <div class="pilar">
            <div class="pilar-icono">✏️</div>
            <h3>Aprendizaje aplicado</h3>
            <p>Conecta la teoría con el análisis de casos, ejercicios de observación y situaciones de la práctica profesional.</p>
          </div>

          <div class="pilar">
            <div class="pilar-icono">🛡️</div>
            <h3>Ética en cada decisión</h3>
            <p>Desarrolla criterio para cuidar la dignidad, la diversidad y la confidencialidad de las personas.</p>
          </div>

          <div class="pilar">
            <div class="pilar-icono">💬</div>
            <h3>Mirada interdisciplinaria</h3>
            <p>Dialoga con las ciencias humanas para comprender a cada persona dentro de su realidad social y cultural.</p>
          </div>
        </div>
      </div>
    </section>

    <section class="seccion-clara">
      <div class="contenedor hero-grid">
        <div>
          <img style="width:100%; height:360px; object-fit:cover; border-radius:12px;"
               src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?auto=format&fit=crop&w=900&q=80"
               alt="Estudiantes y docentes conversando">
          <p class="pie-foto">El diálogo y la reflexión compartida también son formas de aprender.</p>
        </div>

        <div>
          <p class="etiqueta">Somos Savia</p>
          <h2>Comprender a la persona.<br>Considerar su mundo.</h2>
          <p class="descripcion">
            Savia es una propuesta de formación en psicología y ciencias humanas que sitúa a las personas
            en el centro. Entendemos la salud mental desde sus dimensiones biológicas, emocionales y sociales.
          </p>
          <p class="descripcion">
            Por eso, conectamos el estudio con la reflexión crítica y el diálogo: para desarrollar una mirada
            sensible, fundamentada y abierta a la complejidad de cada historia.
          </p>
          <div style="margin-top: 24px; display: flex; gap: 22px; flex-wrap: wrap;">
            <a href="#nosotros" class="enlace-flecha" onclick="mostrarVista('nosotros', event)">Conoce a Savia ↗</a>
            <a href="#solicitar-info" class="enlace-flecha" onclick="mostrarVista('solicitar-info', event)">Solicitar folleto ↗</a>
          </div>
        </div>
      </div>
    </section>

    <!-- =========================================================
         VISTA PREVIA TAREA 5: MI RUTA VOCACIONAL (FUNCIÓN EN DESARROLLO)
         ========================================================= -->
    <section class="seccion-preview-funcion" id="mi-ruta-preview">
      <div class="contenedor">
        <span class="badge-desarrollo">Función en desarrollo · Vista previa (Próxima etapa)</span>
        <h2>Mi ruta vocacional y orientación</h2>
        <p class="descripcion">
          En la siguiente etapa del proyecto podrás crear tu cuenta con <strong>Supabase Auth</strong> para guardar
          tu especialidad favorita, conservar tus dudas sobre la carrera y dar seguimiento a tu proceso de orientación.
        </p>

        <div class="preview-grid">
          <!-- Tarjeta izquierda: Interfaz prevista -->
          <div class="preview-card">
            <div class="auth-mockup-bar">
              <div>
                <strong>Acceso de aspirante (Supabase Auth)</strong>
                <span style="display:block; font-size:11px; color:var(--gris);">Inicia sesión con tu correo para conservar tu selección</span>
              </div>
              <span style="font-size:11px; background:white; padding:5px 10px; border-radius:6px; border:1px solid var(--borde);">
                Estado: Vista previa
              </span>
            </div>

            <div class="campo">
              <label for="prev-nombre">Nombre completo *</label>
              <input type="text" id="prev-nombre" placeholder="Ej. Mariana Soto" oninput="actualizarVistaPrevia()">
            </div>

            <div class="campo">
              <label for="prev-correo">Correo electrónico *</label>
              <input type="email" id="prev-correo" placeholder="aspirante@ejemplo.com" oninput="actualizarVistaPrevia()">
            </div>

            <div class="campo">
              <label>Especialidad favorita *</label>
              <div class="chips-especialidad">
                <button type="button" class="chip-esp activo" onclick="elegirEspecialidadPreview('Clínica', this)">♡ Clínica</button>
                <button type="button" class="chip-esp" onclick="elegirEspecialidadPreview('Educativa', this)">📖 Educativa</button>
                <button type="button" class="chip-esp" onclick="elegirEspecialidadPreview('Organizacional', this)">⌘ Organizacional</button>
                <button type="button" class="chip-esp" onclick="elegirEspecialidadPreview('Social', this)">○ Social</button>
                <button type="button" class="chip-esp" onclick="elegirEspecialidadPreview('Neuropsicología', this)">🧠 Neuropsicología</button>
                <button type="button" class="chip-esp" onclick="elegirEspecialidadPreview('Del desarrollo', this)">🌿 Del desarrollo</button>
              </div>
            </div>

            <div class="fila-2">
              <div class="campo">
                <label for="prev-modalidad">Modalidad preferida (opcional)</label>
                <select id="prev-modalidad" onchange="actualizarVistaPrevia()">
                  <option value="Presencial">Presencial</option>
                  <option value="Híbrida">Híbrida</option>
                </select>
              </div>

              <div class="campo">
                <label for="prev-nota">Pregunta o nota (opcional)</label>
                <input type="text" id="prev-nota" placeholder="Ej. Dudas sobre prácticas en 7.º semestre" oninput="actualizarVistaPrevia()">
              </div>
            </div>

            <button type="button" class="boton" onclick="simularVistaPrevia()">
              Previsualizar mi selección (Función en desarrollo)
            </button>

            <div class="aviso-no-persiste">
              <strong>Nota académica:</strong> Esta sección es una vista previa visual. Todavía no crea cuentas reales ni almacena datos en una base de datos.
            </div>
          </div>

          <!-- Tarjeta derecha: Cómo se verá la respuesta guardada -->
          <div class="preview-card dashed">
            <p class="etiqueta" style="margin-bottom:8px;">Así se verá tu panel guardado</p>
            <h3 style="font-size:22px; margin-bottom:10px;">Resumen de tu interés</h3>
            <p style="font-size:12px; color:var(--gris);">
              Cuando se conecte la persistencia de datos, podrás consultar y actualizar esta ficha cada vez que regreses a Savia:
            </p>

            <div class="resumen-guardado-box">
              <p style="font-size:11px; color:#627851; font-weight:bold; text-transform:uppercase; letter-spacing:1px;">
                Ficha de aspirante (Muestra)
              </p>
              <p style="font-size:13px; margin-top:8px;">
                <strong>Aspirante:</strong> <span id="out-nombre">Sin especificar</span>
              </p>
              <p style="font-size:13px; margin-top:4px;">
                <strong>Correo vinculado:</strong> <span id="out-correo">aspirante@ejemplo.com</span>
              </p>
              <p style="font-size:13px; margin-top:4px;">
                <strong>Especialidad favorita:</strong> <span id="out-esp">Clínica</span>
              </p>
              <p style="font-size:13px; margin-top:4px;">
                <strong>Modalidad:</strong> <span id="out-mod">Presencial</span>
              </p>
              <p style="font-size:13px; margin-top:4px;">
                <strong>Nota guardada:</strong> <span id="out-nota">Ninguna nota agregada</span>
              </p>
            </div>

            <div id="feedback-preview" class="mensaje-exito" style="margin-top:14px;">
              ✓ Vista previa actualizada en pantalla. Al recargar la página estos datos se borrarán porque la base de datos aún está en desarrollo.
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="cta-final">
      <div class="contenedor cta-grid">
        <div>
          <p class="etiqueta">Da el siguiente paso</p>
          <h2>Tu vocación puede ser el inicio de un cambio.</h2>
          <p>
            Conoce la propuesta formativa y prepara tu solicitud. Te acompañamos para elegir con
            información y confianza.
          </p>
        </div>
        <div class="cta-derecha">
          <a href="#inscribirme" class="boton" onclick="mostrarVista('inscribirme', event)">Inscribirme ↗</a>
          <small>orientacion@savia.example</small>
          <small style="font-size: 9.5px; opacity: 0.8;">Contacto ilustrativo</small>
        </div>
      </div>
    </section>
  </main>

  <!-- =========================================================
       VISTA 2: CONOCE EL PROGRAMA
       ========================================================= -->
  <main id="vista-programa" class="vista">
    <section class="hero" style="padding-bottom: 30px;">
      <div class="contenedor hero-grid">
        <div>
          <p class="etiqueta">Conoce el programa</p>
          <h1>Licenciatura en Psicología y Ciencias Humanas</h1>
          <p class="hero-descripcion">
            Una formación para comprender la conducta, escuchar con sensibilidad y actuar con criterio.
            Integra las ciencias psicológicas con una mirada ética, social y humana.
          </p>

          <div class="pill-acreditacion">
            <span>🛡️</span> Acreditación por confirmar
          </div>

          <div class="hero-acciones">
            <a href="#inscribirme" class="boton" onclick="mostrarVista('inscribirme', event)">
              Inscribirme a este programa ↗
            </a>
            <a href="#solicitar-info" class="enlace-flecha" onclick="mostrarVista('solicitar-info', event)">
              Solicitar folleto ↗
            </a>
          </div>
        </div>

        <div>
          <img class="imagen-arco"
               src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?auto=format&fit=crop&w=900&q=80"
               alt="Seminario en grupo">
          <p class="pie-foto">El diálogo y la reflexión compartida también son formas de aprender.</p>
        </div>
      </div>

      <div class="contenedor">
        <div class="datos-programa">
          <div class="dato-item">
            <small>Duración</small>
            <strong>4 años · 8 semestres</strong>
          </div>
          <div class="dato-item">
            <small>Modalidad</small>
            <strong>Presencial / Híbrida</strong>
          </div>
          <div class="dato-item">
            <small>Próximo ingreso</small>
            <strong>16 de agosto de 2027</strong>
          </div>
          <div class="dato-item">
            <small>Grado propuesto</small>
            <strong>Licenciatura</strong>
          </div>
        </div>
        <p class="nota-pie-seccion">
          Información ilustrativa · Duración, modalidades, calendario y grado propuestos. Validez oficial y acreditación pendientes de verificación.
        </p>
      </div>
    </section>

    <section class="seccion-clara" style="padding-top: 40px;">
      <div class="contenedor">
        <div class="encabezado-doble">
          <div>
            <p class="etiqueta">Tu recorrido académico</p>
            <h2>Una base integral.<br>Una mirada propia.</h2>
          </div>
          <div class="encabezado-doble-lado">
            <p>
              Del estudio de los procesos básicos a la práctica supervisada: un recorrido progresivo
              para conectar teoría y contexto.
            </p>
          </div>
        </div>

        <div class="recorrido-grid">
          <div class="acordeon-lista">
            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <div>
                  <span class="semestre-num">1.er semestre</span>
                  <span class="acordeon-titulo">Fundamentos para comprender a la persona</span>
                </div>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                <ul class="materias-lista">
                  <li>📖 Introducción a la psicología</li>
                  <li>📖 Bases biológicas de la conducta</li>
                  <li>📖 Historia y pensamiento de las ciencias humanas</li>
                  <li>📖 Lectura y escritura académica</li>
                  <li>📖 Ética y derechos humanos</li>
                </ul>
                <p class="semestre-meta">5 asignaturas · Tronco común</p>
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <div>
                  <span class="semestre-num">2.º semestre</span>
                  <span class="acordeon-titulo">Procesos psicológicos y desarrollo humano</span>
                </div>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                <ul class="materias-lista">
                  <li>📖 Sensación, percepción y atención</li>
                  <li>📖 Desarrollo humano en la infancia y adolescencia</li>
                  <li>📖 Filosofía y epistemología de la psicología</li>
                  <li>📖 Estadística aplicada a las ciencias sociales</li>
                </ul>
                <p class="semestre-meta">4 asignaturas · Tronco común</p>
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <div>
                  <span class="semestre-num">3.er semestre</span>
                  <span class="acordeon-titulo">Evaluación y métodos de investigación</span>
                </div>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                <ul class="materias-lista">
                  <li>📖 Metodología de la investigación cuantitativa</li>
                  <li>📖 Metodología de la investigación cualitativa</li>
                  <li>📖 Entrevista psicológica y observación</li>
                  <li>📖 Memoria, pensamiento y lenguaje</li>
                </ul>
                <p class="semestre-meta">4 asignaturas · Tronco común</p>
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <div>
                  <span class="semestre-num">4.º semestre</span>
                  <span class="acordeon-titulo">Aprendizaje, grupos y contextos sociales</span>
                </div>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                <ul class="materias-lista">
                  <li>📖 Teorías del aprendizaje y cognición</li>
                  <li>📖 Psicología social y dinámicas grupales</li>
                  <li>📖 Adultez y envejecimiento</li>
                  <li>📖 Psicometría y evaluación psicológica</li>
                </ul>
                <p class="semestre-meta">4 asignaturas · Tronco común</p>
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <div>
                  <span class="semestre-num">5.º semestre</span>
                  <span class="acordeon-titulo">Ámbitos de intervención y ética aplicada</span>
                </div>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                <ul class="materias-lista">
                  <li>📖 Introducción a la psicología clínica y de la salud</li>
                  <li>📖 Psicología educativa y procesos escolares</li>
                  <li>📖 Psicología organizacional y del trabajo</li>
                  <li>📖 Bioética y responsabilidad profesional</li>
                </ul>
                <p class="semestre-meta">4 asignaturas · Formación disciplinar</p>
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <div>
                  <span class="semestre-num">6.º semestre</span>
                  <span class="acordeon-titulo">Profundización en áreas de interés</span>
                </div>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                <ul class="materias-lista">
                  <li>📖 Seminario de especialización I</li>
                  <li>📖 Intervención comunitaria y políticas públicas</li>
                  <li>📖 Neuropsicología clínica y evaluación cognitiva</li>
                  <li>📖 Diseño de proyectos de intervención</li>
                </ul>
                <p class="semestre-meta">4 asignaturas · Trayectoria electiva</p>
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <div>
                  <span class="semestre-num">7.º semestre</span>
                  <span class="acordeon-titulo">Prácticas supervisadas y proyecto de investigación</span>
                </div>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                <ul class="materias-lista">
                  <li>📖 Prácticas profesionales supervisadas I</li>
                  <li>📖 Seminario de investigación y tesis I</li>
                  <li>📖 Seminario de especialización II</li>
                </ul>
                <p class="semestre-meta">3 asignaturas · Práctica supervisada</p>
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <div>
                  <span class="semestre-num">8.º semestre</span>
                  <span class="acordeon-titulo">Integración profesional y trabajo de titulación</span>
                </div>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                <ul class="materias-lista">
                  <li>📖 Prácticas profesionales supervisadas II</li>
                  <li>📖 Seminario de titulación e integración</li>
                  <li>📖 Ética y ejercicio profesional contemporáneo</li>
                </ul>
                <p class="semestre-meta">3 asignaturas · Cierre formativo</p>
              </div>
            </div>

            <p class="nota-pie-seccion">
              Información ilustrativa · Plan de estudios orientativo. Asignaturas, secuencia y requisitos sujetos a revisión académica.
            </p>
          </div>

          <div class="sidebar-cards">
            <div class="card-verde-suave">
              <span style="font-size: 20px;">📝</span>
              <h3>La teoría cobra sentido en la práctica.</h3>
              <p>
                Análisis de casos, observación y seminarios de discusión acompañan el aprendizaje.
                Las prácticas se plantean con supervisión y cuidado ético.
              </p>
              <p style="font-size: 11.5px; margin-bottom: 0;">
                <strong>Presencial:</strong> actividades en campus.<br>
                <strong>Híbrida:</strong> encuentros presenciales y trabajo académico a distancia.
              </p>
            </div>

            <div class="card-blanca-borde">
              <h3>Planea tu siguiente paso.</h3>
              <table class="tabla-costos">
                <tr>
                  <td>Inscripción por semestre</td>
                  <td>$2,000 MXN</td>
                </tr>
                <tr>
                  <td>5 mensualidades de</td>
                  <td>$4,800 MXN</td>
                </tr>
                <tr class="total">
                  <td>Total semestral</td>
                  <td>$26,000 MXN</td>
                </tr>
              </table>
              <p style="font-size: 10px; color: var(--gris); margin-bottom: 18px;">
                Información ilustrativa · Materiales y titulación no incluidos. Consulta requisitos y calendario en Inscribirme.
              </p>
              <a href="#inscribirme" class="boton" onclick="mostrarVista('inscribirme', event)">Inscribirme ↗</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="seccion-oscura">
      <div class="contenedor grid-oscuro-2col">
        <div>
          <p class="etiqueta">Perfil de egreso</p>
          <h2>Conocimiento que cuida. Criterio que orienta.</h2>
          <p class="texto-claro">
            Al concluir el recorrido propuesto, podrás integrar evidencia y sensibilidad para comprender
            a las personas dentro de su realidad.
          </p>
        </div>

        <div class="habilidades-lista">
          <div class="habilidad-item">
            <span class="icono-check-circulo">✓</span>
            <div>
              <h3>Comprender y evaluar</h3>
              <p>Analizar procesos psicológicos y seleccionar herramientas de evaluación de manera fundamentada.</p>
            </div>
          </div>

          <div class="habilidad-item">
            <span class="icono-check-circulo">✓</span>
            <div>
              <h3>Investigar y cuestionar</h3>
              <p>Formular preguntas, interpretar evidencia y reconocer los límites de cada intervención.</p>
            </div>
          </div>

          <div class="habilidad-item">
            <span class="icono-check-circulo">✓</span>
            <div>
              <h3>Acompañar con responsabilidad</h3>
              <p>Colaborar con otros profesionales, respetando la diversidad, la confidencialidad y la dignidad humana.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="seccion-clara">
      <div class="contenedor">
        <p class="etiqueta">Horizontes profesionales</p>
        <h2>Muchas formas de aportar al bienestar.</h2>
        <p class="descripcion">
          Seis perspectivas conectadas por una misma formación de base. Explora dónde podrías orientar
          tu desarrollo profesional.
        </p>

        <div class="areas-grid" style="margin-top: 32px;">
          <article class="tarjeta-area-compacta">
            <div class="tarjeta-area-compacta-titulo"><span>♡</span><h3>Clínica</h3></div>
            <p>Centros de salud mental, orientación y programas de prevención.</p>
          </article>

          <article class="tarjeta-area-compacta">
            <div class="tarjeta-area-compacta-titulo"><span>📖</span><h3>Educativa</h3></div>
            <p>Escuelas, orientación educativa y proyectos de inclusión.</p>
          </article>

          <article class="tarjeta-area-compacta">
            <div class="tarjeta-area-compacta-titulo"><span>⌘</span><h3>Organizacional</h3></div>
            <p>Desarrollo de talento, formación y bienestar en el trabajo.</p>
          </article>

          <article class="tarjeta-area-compacta">
            <div class="tarjeta-area-compacta-titulo"><span>○</span><h3>Social</h3></div>
            <p>Asociaciones civiles, proyectos comunitarios y políticas sociales.</p>
          </article>

          <article class="tarjeta-area-compacta">
            <div class="tarjeta-area-compacta-titulo"><span>🧠</span><h3>Neuropsicología</h3></div>
            <p>Equipos de evaluación cognitiva e investigación interdisciplinaria.</p>
          </article>

          <article class="tarjeta-area-compacta">
            <div class="tarjeta-area-compacta-titulo"><span>🌿</span><h3>Del desarrollo</h3></div>
            <p>Centros de desarrollo, atención familiar y programas de envejecimiento.</p>
          </article>
        </div>

        <p class="nota-pie-seccion">
          Información ilustrativa · Ámbitos orientativos, no garantías de empleo. Algunas prácticas requieren formación adicional y habilitación profesional según la normativa aplicable.
        </p>
      </div>
    </section>
  </main>

  <!-- =========================================================
       VISTA 3: ESPECIALIDADES
       ========================================================= -->
  <main id="vista-especialidades" class="vista">
    <section class="seccion-clara">
      <div class="contenedor">
        <p class="etiqueta">Especialidades y áreas de enfoque</p>
        <h1>Seis perspectivas.<br>Una misma mirada humana.</h1>
        <p class="descripcion">
          En Savia, las especialidades no fragmentan la comprensión de la persona: permiten profundizar
          en distintos contextos desde una formación científica y ética común.
        </p>

        <div style="margin-top: 20px;">
          <a href="#mi-ruta-preview" class="enlace-flecha" onclick="irAMiRuta(event)">
            Guardar mi especialidad favorita (Vista previa) ↗
          </a>
        </div>

        <div class="areas-grid" style="margin-top: 32px;">
          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top"><div class="caja-icono">♡</div></div>
              <p class="sub-etiqueta">Salud y bienestar</p>
              <h3>Clínica</h3>
              <p>Comprende los procesos emocionales y las bases de la evaluación y el acompañamiento psicológico.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top"><div class="caja-icono">📖</div></div>
              <p class="sub-etiqueta">Aprendizaje y desarrollo</p>
              <h3>Educativa</h3>
              <p>Explora cómo aprendemos y cómo crear entornos educativos inclusivos en las distintas etapas de la vida.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top"><div class="caja-icono">⌘</div></div>
              <p class="sub-etiqueta">Personas y trabajo</p>
              <h3>Organizacional</h3>
              <p>Promueve el bienestar laboral, el desarrollo del talento y relaciones más saludables en las organizaciones.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top"><div class="caja-icono">○</div></div>
              <p class="sub-etiqueta">Comunidad y cambio</p>
              <h3>Social</h3>
              <p>Analiza los vínculos entre las personas y su entorno para impulsar la participación y el bienestar colectivo.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top"><div class="caja-icono">🧠</div></div>
              <p class="sub-etiqueta">Cerebro y conducta</p>
              <h3>Neuropsicología</h3>
              <p>Acércate a la relación entre cerebro, cognición y comportamiento desde una perspectiva interdisciplinaria.</p>
            </div>
          </article>

          <article class="tarjeta-area">
            <div>
              <div class="tarjeta-area-top"><div class="caja-icono">🌿</div></div>
              <p class="sub-etiqueta">Ciclo vital y vínculos</p>
              <h3>Del desarrollo</h3>
              <p>Estudia los cambios cognitivos, afectivos y sociales desde la infancia hasta el envejecimiento.</p>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section class="seccion-oscura">
      <div class="contenedor grid-oscuro-2col" style="align-items: center;">
        <div>
          <p class="etiqueta">Del interés al recorrido académico</p>
          <h2>Una licenciatura.<br>Perspectivas que dialogan.</h2>
          <p class="texto-claro">
            Empieza por una base científica y humanista compartida. Después, profundiza en tus intereses
            mediante asignaturas, proyectos y prácticas supervisadas.
          </p>
        </div>

        <div class="tarjeta-blanca-oscura">
          <h3>Conoce el programa completo.</h3>
          <ul>
            <li>4 años · 8 semestres</li>
            <li>Modalidad Presencial / Híbrida</li>
            <li>Ingreso previsto: 16 de agosto de 2027</li>
          </ul>
          <a href="#programa" class="enlace-flecha" onclick="mostrarVista('programa', event)">Ver plan de estudios ↗</a>
          <p class="nota-pie-seccion" style="margin-top: 16px;">
            Información ilustrativa · Estructura y calendario propuestos.
          </p>
        </div>
      </div>
    </section>

    <section class="seccion-clara">
      <div class="contenedor grid-oscuro-2col">
        <div>
          <p class="etiqueta">Tu curiosidad es un buen comienzo</p>
          <h2>Elige desde tus preguntas, no desde la prisa.</h2>
        </div>

        <div class="habilidades-lista">
          <div>
            <h3 style="font-size: 19px;">Observa lo que te interesa</h3>
            <p style="font-size: 12.5px; color: var(--gris); margin-top: 5px;">
              ¿Te atraen los procesos de aprendizaje, los vínculos comunitarios o la relación entre cerebro y conducta?
            </p>
          </div>

          <div>
            <h3 style="font-size: 19px;">Revisa el recorrido</h3>
            <p style="font-size: 12.5px; color: var(--gris); margin-top: 5px;">
              Compara las asignaturas del plan y reconoce los conocimientos que comparten todas las áreas.
            </p>
          </div>

          <div>
            <h3 style="font-size: 19px;">Conversa con orientación</h3>
            <p style="font-size: 12.5px; color: var(--gris); margin-top: 5px;">
              Escríbenos a orientacion@savia.example para plantear tus dudas. Contacto ilustrativo.
            </p>
          </div>
        </div>
      </div>
    </section>

    <section class="cta-final">
      <div class="contenedor cta-grid">
        <div>
          <p class="etiqueta">Da el siguiente paso</p>
          <h2>Tu vocación puede ser el inicio de un cambio.</h2>
          <p>
            Conoce la propuesta formativa y prepara tu solicitud. Te acompañamos para elegir con
            información y confianza.
          </p>
        </div>
        <div class="cta-derecha">
          <a href="#inscribirme" class="boton" onclick="mostrarVista('inscribirme', event)">Inscribirme a este programa ↗</a>
          <small>orientacion@savia.example</small>
          <small style="font-size: 9.5px; opacity: 0.8;">Contacto ilustrativo</small>
        </div>
      </div>
    </section>
  </main>

  <!-- =========================================================
       VISTA 4: NOSOTROS
       ========================================================= -->
  <main id="vista-nosotros" class="vista">
    <section class="seccion-clara">
      <div class="contenedor hero-grid">
        <div>
          <p class="etiqueta">Nosotros · Identidad académica</p>
          <h1>Una comunidad que piensa y acompaña.</h1>
          <p class="hero-descripcion">
            Savia nace como una propuesta formativa que entiende la psicología en diálogo constante
            con las ciencias humanas, la ética y el compromiso social.
          </p>
          <div style="margin-top: 24px;">
            <a href="#faq" class="enlace-flecha" onclick="mostrarVista('faq', event)">Ver preguntas frecuentes ↗</a>
          </div>
        </div>
        <div>
          <img class="imagen-arco"
               src="https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?auto=format&fit=crop&w=900&q=80"
               alt="Encuentro académico">
        </div>
      </div>
    </section>

    <section class="seccion-verde-claro">
      <div class="contenedor">
        <div class="encabezado-doble">
          <div>
            <p class="etiqueta">Quienes acompañan tu formación</p>
            <h2>El conocimiento también<br>es encuentro.</h2>
          </div>
          <div class="encabezado-doble-lado">
            <p>Un equipo que propone preguntas y abre conversaciones entre disciplinas.</p>
          </div>
        </div>

        <div class="tarjetas-docentes">
          <article class="docente">
            <div class="docente-persona">
              <img src="https://images.unsplash.com/photo-1551836022-d5d88e9218df?auto=format&fit=crop&w=300&q=80"
                   alt="Elena Robles">
              <div>
                <h3>Elena Robles</h3>
                <p class="especialidad">Decana · Ética y práctica clínica</p>
              </div>
            </div>
            <p>Acompaña el desarrollo del criterio profesional y la escucha responsable.</p>
          </article>

          <article class="docente">
            <div class="docente-persona">
              <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&w=300&q=80"
                   alt="Martín Vidal">
              <div>
                <h3>Martín Vidal</h3>
                <p class="especialidad">Psicología social y comunitaria</p>
              </div>
            </div>
            <p>Conecta la investigación cualitativa con el análisis de los vínculos sociales.</p>
          </article>

          <article class="docente">
            <div class="docente-persona">
              <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=300&q=80"
                   alt="Lucía Montes">
              <div>
                <h3>Lucía Montes</h3>
                <p class="especialidad">Neurociencias y aprendizaje</p>
              </div>
            </div>
            <p>Explora las relaciones entre cognición, contexto y procesos de aprendizaje.</p>
          </article>
        </div>

        <p class="nota-pie-seccion">
          Información ilustrativa · Nombres, perfiles y retratos docentes ficticios.
        </p>
      </div>
    </section>

    <section class="cta-final" style="border-top: 1px solid rgba(32,61,47,0.1);">
      <div class="contenedor cta-grid">
        <div>
          <p class="etiqueta">Da el siguiente paso</p>
          <h2>Tu vocación puede ser el inicio de un cambio.</h2>
          <p>
            Conoce la propuesta formativa y prepara tu solicitud. Te acompañamos para elegir con
            información y confianza.
          </p>
        </div>
        <div class="cta-derecha">
          <a href="#inscribirme" class="boton" onclick="mostrarVista('inscribirme', event)">Inscribirme a este programa ↗</a>
          <small>orientacion@savia.example</small>
          <small style="font-size: 9.5px; opacity: 0.8;">Contacto ilustrativo</small>
        </div>
      </div>
    </section>
  </main>

  <!-- =========================================================
       VISTA 5: INSCRIBIRME (ADMISIONES)
       ========================================================= -->
  <main id="vista-inscribirme" class="vista">
    <section class="seccion-clara" style="padding-bottom: 60px;">
      <div class="contenedor">
        <p class="etiqueta">Admisiones · Convocatoria agosto 2027</p>
        <h1>Empieza a cultivar tu vocación.</h1>
        <p class="descripcion">
          Queremos conocer tus intereses y acompañarte en el ingreso. Reúne tus documentos y completa
          la solicitud de la Licenciatura en Psicología y Ciencias Humanas.
        </p>

        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 10px; margin-top: 14px;">
          <span style="font-size: 10px; color: var(--gris);">Información ilustrativa · Convocatoria, fechas y costos de ejemplo.</span>
          <a href="#programa" class="enlace-flecha" onclick="mostrarVista('programa', event)">Conoce el programa ↗</a>
        </div>

        <div class="pasos-barra">
          <div class="paso-pill activo">
            <span class="paso-num">1</span>
            <span>1. Datos personales</span>
          </div>
          <div class="paso-pill">
            <span class="paso-num">2</span>
            <span>2. Selección de programa</span>
          </div>
          <div class="paso-pill">
            <span class="paso-num">3</span>
            <span>3. Documentación</span>
          </div>
        </div>
        <p style="font-size: 10.5px; color: var(--gris);">
          Los tres apartados están visibles a continuación. Los campos marcados con * son obligatorios.
        </p>

        <div class="admisiones-grid">
          <form class="formulario-caja" onsubmit="mostrarMensajeExito(event, 'exito-inscripcion')">
            <div class="form-bloque">
              <div class="form-bloque-titulo">
                <span class="badge-num">1</span>
                <h3>Datos personales</h3>
              </div>

              <div class="campo">
                <label for="nombre">Nombre completo *</label>
                <input type="text" id="nombre" value="Ana García López" required>
                <small>Escríbelo tal como aparece en tu identificación oficial.</small>
              </div>

              <div class="fila-2">
                <div class="campo">
                  <label for="correo">Correo electrónico *</label>
                  <input type="email" id="correo" value="ana.garcia@example.com" required>
                  <small>Aquí recibirás el seguimiento de tu solicitud.</small>
                </div>

                <div class="campo">
                  <label for="telefono">Teléfono de contacto *</label>
                  <input type="tel" id="telefono" value="+52 55 0100 0200" required>
                  <small>Incluye el código de país y de área.</small>
                </div>
              </div>

              <small style="font-size: 10px; color: var(--gris);">Datos personales de ejemplo. No corresponden a una aspirante real.</small>
            </div>

            <div class="form-bloque">
              <div class="form-bloque-titulo">
                <span class="badge-num">2</span>
                <h3>Selección de programa</h3>
              </div>

              <div class="campo">
                <label for="prog">Programa de interés *</label>
                <select id="prog">
                  <option>Licenciatura en Psicología y Ciencias Humanas</option>
                </select>
                <small>Formación de 4 años · 8 semestres. Inicio previsto: 16 de agosto de 2027.</small>
              </div>

              <div class="fila-2">
                <div class="campo">
                  <label for="modalidad">Modalidad preferida *</label>
                  <select id="modalidad">
                    <option>Híbrida</option>
                    <option>Presencial</option>
                  </select>
                  <small>También disponible en modalidad Presencial.</small>
                </div>

                <div class="campo">
                  <label for="area-interes">Área que te interesa</label>
                  <select id="area-interes">
                    <option>Clínica</option>
                    <option>Educativa</option>
                    <option>Organizacional</option>
                    <option>Social</option>
                    <option>Neuropsicología</option>
                    <option>Del desarrollo</option>
                  </select>
                  <small>Es orientativa; no limita tu formación.</small>
                </div>
              </div>
            </div>

            <div class="form-bloque" style="border-bottom: none; padding-bottom: 0;">
              <div class="form-bloque-titulo">
                <span class="badge-num">3</span>
                <h3>Documentación</h3>
              </div>

              <p style="font-size: 12px; color: var(--gris);">
                Adjunta identificación oficial, certificado de bachillerato o constancia de estudios y una carta de motivos de hasta una página.
              </p>

              <div class="zona-archivo">
                <span style="font-size: 22px;">☁️</span>
                <strong>Arrastra tus documentos o selecciona archivos</strong>
                <span>PDF, JPG o PNG · Máximo 10 MB por archivo</span>
                <input type="file" id="archivo-input" style="display: none;" onchange="actualizarArchivo(this)">
                <button type="button" class="btn-secundario" onclick="document.getElementById('archivo-input').click()">
                  Seleccionar archivos
                </button>
              </div>

              <div class="archivo-adjunto" id="archivo-preview">
                <div>
                  📄 <strong id="nombre-archivo">carta_de_motivos.pdf</strong>
                  <span style="display:block; font-size: 10px; color: var(--gris); margin-left: 20px;">
                    248 KB · Listo para adjuntar · Archivo de ejemplo
                  </span>
                </div>
                <button type="button" style="background:none; border:none; color:var(--gris);" onclick="this.parentElement.style.display='none'">✕</button>
              </div>
            </div>

            <div style="border-top: 1px solid var(--borde); padding-top: 20px; margin-top: 20px;">
              <label class="checkbox-privacidad">
                <input type="checkbox" checked required>
                <span>He leído el aviso de privacidad y autorizo el uso de mis datos para evaluar y dar seguimiento a esta solicitud. *</span>
              </label>
              <p style="font-size: 10.5px; color: var(--gris); margin-left: 22px;">
                Tus datos se destinarían exclusivamente al proceso de admisión. No incluyas información clínica sensible.
                Podrías solicitar acceso, rectificación o eliminación en privacidad@savia.example (contacto ilustrativo).
              </p>

              <div class="envio-fila">
                <button type="submit" class="boton">Enviar solicitud ↗</button>
                <span style="font-size: 11px; color: var(--gris);">La solicitud no implica inscripción ni compromiso de pago.</span>
              </div>

              <div id="exito-inscripcion" class="mensaje-exito">
                ✓ Solicitud registrada de forma ilustrativa. Nuestro equipo de orientación revisará tus datos y se pondrá en contacto contigo.
              </div>
            </div>
          </form>

          <div class="sidebar-cards">
            <div class="card-verde-suave">
              <p class="etiqueta" style="margin-bottom: 6px;">Tu próximo ciclo</p>
              <h3 style="margin-top: 0;">Agosto 2027</h3>

              <p style="margin-bottom: 10px;">
                <strong>Recepción de solicitudes</strong><br>
                1 de marzo–30 de junio de 2027
              </p>
              <p style="margin-bottom: 10px;">
                <strong>Entrevistas de orientación</strong><br>
                5–16 de julio de 2027
              </p>
              <p style="margin-bottom: 12px;">
                <strong>Inicio de clases</strong><br>
                16 de agosto de 2027
              </p>
              <span style="font-size: 9.5px; color: var(--texto); opacity: 0.8;">Información ilustrativa · Fechas de una convocatoria de ejemplo.</span>
            </div>

            <div class="card-blanca-borde">
              <h3>Tu inversión académica</h3>
              <p style="font-size: 11.5px; color: var(--gris);">
                Importes en pesos mexicanos (MXN). Mismo esquema para Presencial e Híbrida.
              </p>
              <table class="tabla-costos">
                <tr>
                  <td>Inscripción por semestre</td>
                  <td>$2,000</td>
                </tr>
                <tr>
                  <td>Colegiatura mensual</td>
                  <td>$4,800</td>
                </tr>
                <tr>
                  <td>Mensualidades por semestre</td>
                  <td>5</td>
                </tr>
                <tr class="total">
                  <td>Total por semestre</td>
                  <td>$26,000</td>
                </tr>
              </table>
              <p style="font-size: 9.5px; color: var(--gris);">
                Información ilustrativa · No es una cotización. Materiales y trámites de titulación no incluidos; importes por confirmar.
              </p>
            </div>

            <div class="card-blanca-borde" style="background: var(--verde-suave);">
              <span style="font-size: 18px;">💬</span>
              <h3 style="margin-top: 8px;">No tienes que decidir a solas.</h3>
              <p style="font-size: 12px; color: var(--gris); margin-bottom: 12px;">
                Si aún no cuentas con tu certificado o tienes dudas sobre la modalidad, consulta con orientación antes de preparar tu solicitud.
              </p>
              <strong style="font-size: 12px; display: block;">orientacion@savia.example</strong>
              <span style="font-size: 10.5px; color: var(--gris); display: block; margin-top: 4px;">
                Lunes a viernes · 09:00–18:00 h<br>
                Contacto y horario ilustrativos.
              </span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="seccion-verde-claro">
      <div class="contenedor">
        <h2 style="margin-bottom: 35px;">Una solicitud, un primer encuentro.</h2>
        <div class="tarjetas-docentes" style="background: transparent;">
          <div>
            <h3 style="font-size: 20px; margin-bottom: 8px;">Revisión documental</h3>
            <p style="font-size: 12.5px; color: var(--texto); opacity: 0.85;">
              El equipo revisaría tus datos y te indicaría si falta algún documento.
            </p>
          </div>
          <div>
            <h3 style="font-size: 20px; margin-bottom: 8px;">Conversación de orientación</h3>
            <p style="font-size: 12.5px; color: var(--texto); opacity: 0.85;">
              Un espacio para conocer tus motivaciones y resolver tus preguntas sobre la carrera.
            </p>
          </div>
          <div>
            <h3 style="font-size: 20px; margin-bottom: 8px;">Decisión informada</h3>
            <p style="font-size: 12.5px; color: var(--texto); opacity: 0.85;">
              Recibirías los siguientes pasos y las condiciones antes de formalizar tu inscripción.
            </p>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- =========================================================
       VISTA 6: PREGUNTAS FRECUENTES (FAQ)
       ========================================================= -->
  <main id="vista-faq" class="vista">
    <section class="seccion-clara">
      <div class="contenedor">
        <nav class="breadcrumb" aria-label="Ruta de navegación">
          <a href="#inicio" onclick="mostrarVista('inicio', event)">Inicio</a>
          <span>/</span>
          <span>Preguntas frecuentes</span>
        </nav>

        <p class="etiqueta">Orientación para aspirantes</p>
        <h1>Preguntas frecuentes</h1>
        <p class="descripcion">
          Elegir tu formación merece respuestas claras. Reunimos las dudas más habituales para
          acompañarte antes de dar el siguiente paso.
        </p>

        <div class="faq-tabs">
          <button type="button" class="faq-tab activa" onclick="filtrarFaq('todas', this)">Admisiones</button>
          <button type="button" class="faq-tab" onclick="filtrarFaq('requisitos', this)">Requisitos académicos</button>
          <button type="button" class="faq-tab" onclick="filtrarFaq('becas', this)">Becas y colegiaturas</button>
          <button type="button" class="faq-tab" onclick="filtrarFaq('soporte', this)">Soporte técnico</button>
        </div>
        <p style="font-size: 10.5px; color: var(--gris); margin-bottom: 24px;">
          Todas las categorías se presentan a continuación. Haz clic en cada pregunta para abrir o cerrar su respuesta.
        </p>

        <div class="faq-bloque" data-cat="admisiones">
          <div>
            <h3>Admisiones</h3>
            <p>Tu primer acercamiento a Savia.</p>
          </div>

          <div class="acordeon-lista">
            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Cómo puedo iniciar mi proceso de admisión?</span>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                Comienza por solicitar información o consultar la página Inscribirme. Un asesor podrá orientarte sobre el programa y los pasos de la solicitud. En esta propuesta conceptual no se reciben expedientes ni pagos.
              </div>
            </div>

            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Solicitar información me compromete a inscribirme?</span>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                No. El folleto y la orientación te ayudan a tomar una decisión informada. Antes de cualquier inscripción, solicita por escrito las condiciones, las fechas y la documentación aplicables.
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Puedo conversar con un asesor antes de elegir?</span>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                Sí. Puedes escribir a orientacion@savia.example o solicitar el folleto informativo indicando tu horario de preferencia para recibir orientación personalizada.
              </div>
            </div>
          </div>
        </div>

        <div class="faq-bloque" data-cat="requisitos">
          <div>
            <h3>Requisitos académicos</h3>
            <p>Prepara tu siguiente etapa con claridad.</p>
          </div>

          <div class="acordeon-lista">
            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Qué estudios previos necesito para ingresar?</span>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                Los requisitos dependen del nivel y del programa elegido. Confirma con orientación el grado previo requerido y la documentación aceptada antes de preparar tu expediente; aquí no se publica una convocatoria oficial.
              </div>
            </div>

            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿La propuesta cuenta con acreditación o validez oficial?</span>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                Savia es una identidad académica conceptual y su acreditación no está confirmada. Antes de tomar una decisión, verifica con la institución responsable la autorización y la validez del programa específico.
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Se pueden revisar estudios cursados en otra institución?</span>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                En una implementación operativa, la equivalencia o revalidación de estudios se evaluaría caso por caso conforme al plan de estudios vigente y la normativa educativa aplicable.
              </div>
            </div>
          </div>
        </div>

        <div class="faq-bloque" data-cat="becas">
          <div>
            <h3>Becas y colegiaturas</h3>
            <p>Información para planear, sin sorpresas.</p>
          </div>

          <div class="acordeon-lista">
            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Dónde consulto el costo total del programa?</span>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                Solicita un desglose que distinga inscripción, colegiaturas, materiales y otros conceptos. No se publican importes oficiales en este sitio conceptual; cualquier presupuesto debe indicar vigencia y condiciones.
              </div>
            </div>

            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Cómo puedo conocer las opciones de beca?</span>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                Pregunta por las convocatorias disponibles, los criterios de selección, los documentos y las condiciones de renovación. Este diseño no confirma la existencia de becas ni garantiza apoyos económicos.
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Qué debo revisar antes de realizar un pago?</span>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                Verifica siempre los canales oficiales de pago, los plazos establecidos, los conceptos incluidos y las políticas de reembolso o cancelación antes de realizar cualquier transferencia.
              </div>
            </div>
          </div>
        </div>

        <div class="faq-bloque" data-cat="soporte">
          <div>
            <h3>Soporte técnico</h3>
            <p>Ayuda para consultar la información.</p>
          </div>

          <div class="acordeon-lista">
            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Qué hago si no puedo consultar una página o un documento?</span>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                Anota la página, el dispositivo y el navegador que utilizas. Describe el problema al escribir a orientacion@savia.example. No incluyas contraseñas ni documentos personales; el correo es ilustrativo.
              </div>
            </div>

            <div class="acordeon-item abierto">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Puedo pedir la información en otro formato?</span>
                <span class="acordeon-signo">−</span>
              </button>
              <div class="acordeon-body">
                Sí, puedes plantear la necesidad de un documento legible, texto alternativo u otra vía de orientación. La página Accesibilidad reúne los objetivos previstos y un espacio para describir barreras de acceso.
              </div>
            </div>

            <div class="acordeon-item">
              <button class="acordeon-header" onclick="toggleAcordeon(this)">
                <span class="acordeon-titulo">¿Cómo informo de un error en un formulario?</span>
                <span class="acordeon-signo">+</span>
              </button>
              <div class="acordeon-body">
                Puedes reportarlo desde el formulario «Comparte una mejora» en la vista de Accesibilidad, indicando el nombre de la página y el campo donde ocurrió la incidencia.
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="cta-final">
      <div class="contenedor cta-grid">
        <div>
          <p class="etiqueta">Hablemos con calma</p>
          <h2>Nadie se queda con dudas. Contacta a un asesor</h2>
          <p>
            Comparte lo que necesitas saber y encuentra una orientación más cercana.
          </p>
        </div>
        <div class="cta-derecha" style="text-align: left;">
          <div style="display: flex; gap: 12px; flex-wrap: wrap; margin-bottom: 12px;">
            <a href="#solicitar-info" class="boton" onclick="mostrarVista('solicitar-info', event)">💬 WhatsApp</a>
            <a href="mailto:orientacion@savia.example" class="boton-outline">✉️ Correo electrónico</a>
          </div>
          <strong style="font-size: 12px; display: block;">orientacion@savia.example</strong>
          <small style="font-size: 10px; opacity: 0.85;">
            Canales ilustrativos. WhatsApp sin número asignado; no se envían mensajes desde esta vista.
          </small>
        </div>
      </div>
    </section>
  </main>

  <!-- =========================================================
       VISTA 7: SOLICITAR INFORMACIÓN (FOLLETO)
       ========================================================= -->
  <main id="vista-solicitar-info" class="vista">
    <section class="seccion-clara">
      <div class="contenedor">
        <nav class="breadcrumb" aria-label="Ruta de navegación">
          <a href="#inicio" onclick="mostrarVista('inicio', event)">Inicio</a>
          <span>/</span>
          <span>Solicitar información</span>
        </nav>

        <p class="etiqueta">Tu vocación, con información</p>
        <h1>Solicitar información</h1>
        <p class="descripcion">
          Conoce la propuesta de Savia y decide con calma. Cuéntanos cómo contactarte para orientarte y
          compartir el folleto informativo.
        </p>

        <div class="dos-col-equilibrado" style="margin-top: 42px;">
          <div>
            <h2 style="font-size: 28px; margin-bottom: 26px;">Una formación que empieza por comprender.</h2>

            <div class="habilidades-lista" style="gap: 22px; margin-bottom: 28px;">
              <div class="habilidad-item">
                <div class="caja-icono">📖</div>
                <div>
                  <h3 style="font-size: 15px; font-family: Arial, sans-serif; font-weight: bold;">Comprender con fundamento</h3>
                  <p style="font-size: 12.5px; color: var(--gris); margin-top: 3px;">
                    Una propuesta que conecta el estudio de la conducta con la lectura crítica de la evidencia científica.
                  </p>
                </div>
              </div>

              <div class="habilidad-item">
                <div class="caja-icono">♡</div>
                <div>
                  <h3 style="font-size: 15px; font-family: Arial, sans-serif; font-weight: bold;">Aprender con sentido humano</h3>
                  <p style="font-size: 12.5px; color: var(--gris); margin-top: 3px;">
                    Ética, escucha y atención al contexto para reflexionar sobre el cuidado y el bienestar de las personas.
                  </p>
                </div>
              </div>

              <div class="habilidad-item">
                <div class="caja-icono">🧭</div>
                <div>
                  <h3 style="font-size: 15px; font-family: Arial, sans-serif; font-weight: bold;">Elegir con información</h3>
                  <p style="font-size: 12.5px; color: var(--gris); margin-top: 3px;">
                    Recibe una visión del programa, sus áreas de estudio y las preguntas clave para preparar tu decisión.
                  </p>
                </div>
              </div>
            </div>

            <img style="width: 100%; height: 210px; object-fit: cover; border-radius: 10px;"
                 src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?auto=format&fit=crop&w=800&q=80"
                 alt="Estudiantes conversando">
            <p class="nota-pie-seccion" style="margin-top: 12px;">
              Propuesta académica ilustrativa. La oferta, los requisitos, los costos y la validez oficial deberán confirmarse antes de cualquier inscripción; la acreditación no está confirmada.
            </p>
          </div>

          <form class="formulario-caja" onsubmit="mostrarMensajeExito(event, 'exito-folleto')">
            <p class="etiqueta" style="margin-bottom: 6px;">Conversemos sobre tu futuro</p>
            <h3 style="font-size: 26px; margin-bottom: 8px;">Recibe el folleto</h3>
            <p style="font-size: 12px; color: var(--gris); margin-bottom: 20px;">
              Completa estos cuatro datos. Nombre y correo son necesarios; teléfono y horario son opcionales.
            </p>

            <div class="campo">
              <label for="folleto-nombre">Nombre</label>
              <input type="text" id="folleto-nombre" placeholder="Tu nombre completo" required>
              <small>Escribe cómo prefieres que nos dirijamos a ti.</small>
            </div>

            <div class="campo">
              <label for="folleto-correo">Correo electrónico</label>
              <input type="email" id="folleto-correo" placeholder="nombre@example.com" required>
              <small>Aquí recibirías el folleto y la respuesta a tu consulta.</small>
            </div>

            <div class="campo">
              <label for="folleto-tel">Teléfono</label>
              <input type="tel" id="folleto-tel" placeholder="Código de país y número">
              <small>Opcional. Solo para dar seguimiento a esta solicitud.</small>
            </div>

            <div class="campo">
              <label>Horario preferido</label>
              <div class="horario-opciones">
                <button type="button" class="btn-horario" onclick="seleccionarHorario(this)">Mañana</button>
                <button type="button" class="btn-horario" onclick="seleccionarHorario(this)">Tarde</button>
                <button type="button" class="btn-horario seleccionado" onclick="seleccionarHorario(this)">Sin preferencia</button>
              </div>
              <small>Opcional · Mañana: 09:00–13:00 h · Tarde: 13:00–18:00 h. Horarios ilustrativos de lunes a viernes.</small>
            </div>

            <p style="font-size: 11px; color: var(--gris); margin: 16px 0;">
              Al solicitar el folleto, darías tu consentimiento para utilizar estos datos únicamente para responder y dar seguimiento a tu consulta. No implica inscripción ni autorización para publicidad adicional. Consulta Privacidad.
            </p>

            <button type="submit" class="boton">↗ Recibir folleto informativo</button>

            <div style="border-top: 1px solid var(--borde); margin-top: 22px; padding-top: 14px;">
              <p style="font-size: 10.5px; color: var(--gris);">
                Respuesta prevista: por correo, en el siguiente día hábil de atención. Es una expectativa ilustrativa, no un plazo de servicio confirmado.
              </p>
              <strong style="font-size: 10.5px; display: block; margin-top: 6px;">
                Formulario de muestra: no recopila ni envía datos.
              </strong>
            </div>

            <div id="exito-folleto" class="mensaje-exito">
              ✓ Solicitud de folleto registrada de forma ilustrativa.
            </div>
          </form>
        </div>
      </div>
    </section>
  </main>

  <!-- =========================================================
       VISTA 8: PRIVACIDAD
       ========================================================= -->
  <main id="vista-privacidad" class="vista">
    <section class="seccion-clara">
      <div class="contenedor">
        <nav class="breadcrumb" aria-label="Ruta de navegación">
          <a href="#inicio" onclick="mostrarVista('inicio', event)">Inicio</a>
          <span>/</span>
          <span>Privacidad</span>
        </nav>

        <p class="etiqueta">Transparencia y cuidado</p>
        <h1>Privacidad</h1>
        <p class="descripcion">
          Comprender qué información se solicita y cómo se utilizaría es parte de una relación de confianza.
          Este modelo explica los criterios previstos para cuidar tus datos.
        </p>

        <div class="banner-aviso">
          <strong>Documento modelo · Pendiente de revisión jurídica</strong>
          <p>Contenido orientativo para una institución conceptual. No sustituye un aviso de privacidad definitivo ni acredita que existan tratamientos de datos en funcionamiento.</p>
        </div>

        <div class="legal-grid">
          <aside class="indice-legal">
            <p class="etiqueta">En este documento</p>
            <a href="#priv-alcance">Alcance y responsable</a>
            <a href="#priv-datos">Datos de consulta e inscripción</a>
            <a href="#priv-finalidades">Finalidades y comunicación de datos</a>
            <a href="#priv-consentimiento">Consentimiento y conservación</a>
            <a href="#priv-seguridad">Seguridad y cuidado de la información</a>
            <a href="#priv-arco">Tus derechos ARCO</a>
            <a href="#priv-cookies">Cookies y preferencias</a>
            <a href="#priv-contacto">Contacto y actualizaciones</a>

            <div style="border-top: 1px solid var(--borde); margin-top: 18px; padding-top: 16px;">
              <strong style="font-size: 11px; display: block;">Última actualización</strong>
              <span style="font-size: 11px; color: var(--gris); display: block; margin-top: 4px;">7 de noviembre de 2026</span>
              <span style="font-size: 10.5px; color: var(--gris); display: block; margin-top: 4px;">Revisión jurídica pendiente.</span>
            </div>
          </aside>

          <div>
            <div class="bloque-legal" id="priv-alcance">
              <h2>Alcance y responsable</h2>
              <p>
                Este documento describe el tratamiento de datos que se prevé para una futura implementación del sitio de Savia. Savia es una identidad académica conceptual: no identifica aquí a una institución operadora real. Esta vista estática no recopila información ni constituye un aviso aprobado para un servicio en funcionamiento.
              </p>
              <p>
                Antes de publicar formularios operativos, deberán definirse la identidad y los medios de contacto del responsable, la normativa aplicable y los procedimientos de atención. El texto final deberá someterse a revisión jurídica y ponerse a disposición antes de recabar datos.
              </p>
            </div>

            <div class="bloque-legal" id="priv-datos">
              <h2>Datos de consulta e inscripción</h2>
              <p>
                Para una consulta informativa se prevén nombre, correo electrónico y, de forma opcional, teléfono y horario preferido. Estos datos permitirían responder y acordar un medio de contacto. El formulario de accesibilidad prevé un contacto, la página afectada y una descripción de la barrera; no requiere información de salud.
              </p>
              <p>
                En un eventual proceso de inscripción podrían solicitarse datos de identificación y contacto, antecedentes académicos y documentos que acrediten estudios previos. La lista definitiva deberá explicarse en la convocatoria correspondiente. No envíes identificaciones, datos bancarios ni expedientes sensibles a los correos de ejemplo.
              </p>
            </div>

            <div class="bloque-legal" id="priv-finalidades">
              <h2>Finalidades y comunicación de datos</h2>
              <p>
                Las finalidades previstas son atender preguntas, entregar información solicitada, orientar a aspirantes y, si se inicia un proceso separado, revisar una solicitud de admisión y gestionar la relación académica. Cada trámite deberá solicitar únicamente la información necesaria para su finalidad.
              </p>
              <p>
                El envío de novedades o campañas sería una finalidad opcional, con una elección independiente que no condicionaría la atención. Si se utilizan proveedores de alojamiento, correo o gestión académica, deberán identificarse sus funciones y evaluarse sus condiciones de acceso, confidencialidad y transferencias. Este modelo no confirma proveedores ni cesiones actuales.
              </p>
            </div>

            <div class="bloque-legal" id="priv-consentimiento">
              <h2>Consentimiento y conservación</h2>
              <p>
                Antes de enviar información, la versión operativa deberá explicar el uso previsto y recabar el consentimiento que corresponda. La persona podrá consultar cómo retirar un consentimiento para usos opcionales, sin afectar el tratamiento previo que hubiera sido válido ni las obligaciones que resulten aplicables.
              </p>
              <p>
                Los datos de consulta se conservarían mientras sea necesario atender la solicitud y resolver su seguimiento. Los expedientes de inscripción requerirían plazos específicos según su finalidad y las obligaciones aplicables. La política definitiva deberá fijar esos plazos, los criterios de bloqueo y la eliminación o anonimización; este modelo no establece un periodo legal de conservación.
              </p>
            </div>

            <div class="bloque-legal" id="priv-seguridad">
              <h2>Seguridad y cuidado de la información</h2>
              <p>
                La implementación deberá contemplar controles de acceso por función, comunicaciones protegidas, copias de respaldo y procedimientos de gestión de incidentes. El acceso a expedientes deberá limitarse a quienes lo necesiten para sus tareas, con revisión periódica de permisos.
              </p>
              <p>
                Estas medidas son criterios de diseño pendientes de implementación y evaluación, no una garantía de seguridad absoluta. Evita incluir contraseñas o información clínica en consultas generales. Si detectas una exposición de datos, describe el problema sin reproducir información de otras personas.
              </p>
            </div>

            <div class="bloque-legal" id="priv-arco">
              <h2>Tus derechos ARCO</h2>
              <p>
                Acceso: conocer qué datos se tratan y para qué. Rectificación: corregir información inexacta o incompleta. Cancelación: solicitar que dejen de tratarse y se eliminen cuando proceda. Oposición: pedir que no se utilicen para determinadas finalidades, según las condiciones de la normativa aplicable.
              </p>
              <p>
                El canal previsto para presentar una solicitud es orientacion@savia.example, con el asunto «Solicitud ARCO». Indica el derecho que deseas ejercer, los datos o el trámite al que se refiere y un medio para recibir respuesta. El responsable deberá establecer un mecanismo proporcional para verificar identidad o representación; no adjuntes documentos sensibles al primer mensaje.
              </p>
              <p>
                La atención deberá informar la recepción, las aclaraciones necesarias y la resolución dentro de los plazos que correspondan a la normativa aplicable. El correo es reservado e ilustrativo: no recibe solicitudes reales. Los plazos y la autoridad competente deberán precisarse en el aviso definitivo.
              </p>
            </div>

            <div class="bloque-legal" id="priv-cookies">
              <h2>Cookies y preferencias</h2>
              <p>
                La versión estática no instala cookies. En un sitio operativo se distinguirían las estrictamente necesarias para seguridad y funcionamiento de las opcionales, como analítica o personalización. Las opcionales deberían permanecer desactivadas hasta que exista una elección informada, específica y revocable.
              </p>

              <div class="caja-cookies">
                <div class="cookie-fila">
                  <strong>Esenciales</strong>
                  <span style="font-size: 11px; color: var(--gris);">Necesarias en la versión operativa</span>
                </div>
                <p style="font-size: 11.5px; margin-bottom: 16px;">
                  Se limitarían a permitir las funciones solicitadas y proteger la sesión; deberán documentarse su finalidad y duración.
                </p>

                <div class="cookie-fila">
                  <strong>Analítica y personalización</strong>
                  <span style="font-size: 11px; color: var(--gris);">Desactivadas</span>
                </div>

                <div style="display: flex; gap: 12px; margin: 14px 0; flex-wrap: wrap;">
                  <button type="button" class="boton" style="padding: 10px 18px;" onclick="alert('Preferencias de muestra: Solo cookies esenciales activas.')">Solo esenciales</button>
                  <button type="button" class="boton-outline" style="padding: 10px 18px;" onclick="alert('Panel de preferencias ilustrativo.')">Configurar preferencias</button>
                </div>

                <p style="font-size: 10.5px; margin-bottom: 0;">
                  Controles ilustrativos, sin efecto en esta vista. La versión final deberá permitir cambiar o retirar la elección con la misma facilidad que otorgarla.
                </p>
              </div>
            </div>

            <div class="bloque-legal" id="priv-contacto" style="margin-bottom: 0;">
              <h2>Contacto y actualizaciones</h2>
              <p>
                Para dudas sobre este modelo, el contacto previsto es orientacion@savia.example. Es un correo de ejemplo, no un canal institucional activo. Una versión publicada deberá ofrecer un medio real y accesible para consultas y para el ejercicio de derechos.
              </p>
              <p style="margin-bottom: 0;">
                Los cambios en finalidades, categorías de datos o canales de atención deberán reflejarse en un documento actualizado. Antes de utilizar un formulario operativo, revisa la versión vigente. Última actualización de este modelo: 7 de noviembre de 2026.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- =========================================================
       VISTA 9: ACCESIBILIDAD
       ========================================================= -->
  <main id="vista-accesibilidad" class="vista">
    <section class="seccion-clara">
      <div class="contenedor">
        <nav class="breadcrumb" aria-label="Ruta de navegación">
          <a href="#inicio" onclick="mostrarVista('inicio', event)">Inicio</a>
          <span>/</span>
          <span>Accesibilidad</span>
        </nav>

        <p class="etiqueta">Un espacio para todas las personas</p>
        <h1>Accesibilidad</h1>
        <p class="descripcion">
          Aprender y encontrar orientación no debería depender de cómo ves, escuchas o navegas.
          La accesibilidad forma parte del sitio que queremos construir.
        </p>

        <div class="banner-aviso">
          <strong>Objetivo: WCAG 2.1 nivel AAA · Evaluación pendiente</strong>
          <p>Esta declaración describe comportamientos previstos para la implementación. No afirma conformidad alcanzada ni certificación. Los controles y formularios de esta vista son ilustrativos y no ejecutan acciones.</p>
        </div>

        <div class="dos-col-equilibrado" style="margin-bottom: 50px;">
          <div>
            <p class="etiqueta">Nuestro punto de partida</p>
            <h2>Diseñar para distintas formas de participar.</h2>
            <p class="descripcion">
              WCAG 2.1 organiza sus criterios en cuatro principios: contenido perceptible, operable, comprensible y robusto. El objetivo AAA implica atender también los criterios de niveles A y AA, además de los requisitos más exigentes de contraste, lectura y operación que correspondan.
            </p>
            <p class="descripcion">
              La conformidad deberá comprobarse sobre páginas completas y procesos de principio a fin, con pruebas técnicas y participación de personas con discapacidad. Las decisiones visuales de este diseño, por sí solas, no demuestran cumplimiento.
            </p>
          </div>

          <div class="card-blanca-borde">
            <h3 style="font-size: 24px;">Contraste y lectura</h3>
            <p style="font-size: 12.5px; color: var(--gris);">
              Se prevé ofrecer un modo de alto contraste y conservar la elección. El contenido y las acciones no deberán depender solo del color.
            </p>

            <div class="selector-contraste">
              <button type="button" class="card-contraste estandar" onclick="cambiarContraste(false)">
                <span class="aa">Aa</span>
                <span><span id="dot-estandar">●</span> Estándar</span>
              </button>

              <button type="button" class="card-contraste alto" onclick="cambiarContraste(true)">
                <span class="aa">Aa</span>
                <span><span id="dot-alto">○</span> Alto contraste</span>
              </button>
            </div>

            <p style="font-size: 11px; color: var(--gris); margin-bottom: 10px;">
              El objetivo AAA requiere, entre otros criterios, contraste de al menos 7:1 para texto normal y 4.5:1 para texto grande. Las combinaciones deberán medirse en la implementación.
            </p>
            <strong style="font-size: 10.5px;">Selector interactivo: prueba el modo Estándar o Alto contraste.</strong>
          </div>
        </div>

        <div style="border-top: 1px solid var(--borde); padding-top: 45px;">
          <h2 style="font-size: 28px;">Una ruta clara, también con el teclado.</h2>
          <p class="descripcion">
            La implementación deberá permitir recorrer las funciones sin ratón, con un orden lógico, sin bloqueos de foco y con una vía para saltar al contenido principal.
          </p>

          <div class="teclas-grid">
            <div>
              <span class="tecla-badge">Tab</span>
              <p style="font-size: 12px; color: var(--gris);">Avanzar entre enlaces, campos y controles.</p>
            </div>

            <div>
              <span class="tecla-badge">Shift + Tab</span>
              <p style="font-size: 12px; color: var(--gris);">Volver al elemento anterior en el mismo orden.</p>
            </div>

            <div>
              <span class="tecla-badge">Enter</span>
              <p style="font-size: 12px; color: var(--gris);">Activar un enlace o confirmar un control compatible.</p>
            </div>

            <div>
              <span class="tecla-badge">Escape</span>
              <p style="font-size: 12px; color: var(--gris);">Cerrar un diálogo y devolver el foco al origen.</p>
            </div>
          </div>

          <div class="foco-ejemplo-fila">
            <button type="button" class="btn-foco-demo" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">Ir al contenido</button>
            <div>
              <strong style="font-size: 12.5px; display: block;">Foco visible y persistente</strong>
              <span style="font-size: 12px; color: var(--gris);">
                El contorno deberá identificar dónde estás, sin quedar oculto por menús o cabeceras. Este es un ejemplo visual, no un estado activo.
              </span>
            </div>
          </div>

          <div class="fila-2" style="gap: 45px;">
            <div>
              <h3 style="font-size: 24px; margin-bottom: 10px;">Formularios que orientan</h3>
              <p style="font-size: 12.5px; color: var(--gris);">
                Cada campo deberá tener una etiqueta persistente, instrucciones asociadas y una indicación clara de si es obligatorio. Los errores deberán explicar qué corregir, conservar los datos válidos y poder anunciarse con tecnologías de asistencia, sin depender únicamente del color.
              </p>
            </div>

            <div>
              <h3 style="font-size: 24px; margin-bottom: 10px;">Información que se entiende</h3>
              <p style="font-size: 12.5px; color: var(--gris);">
                Se prevén títulos jerárquicos, lenguaje directo, enlaces descriptivos y alternativas textuales para imágenes relevantes. Los materiales deberán admitir ampliación y reorganización sin perder información. Los términos académicos tendrán explicación y los medios audiovisuales requerirán alternativas adecuadas.
              </p>
            </div>
          </div>

          <div class="banner-aviso" style="margin-top: 38px; margin-bottom: 0;">
            <strong>Estado de revisión · 7 de noviembre de 2026</strong>
            <p>Diseño conceptual. Auditoría WCAG, pruebas con lectores de pantalla, revisión de teclado y evaluación con usuarios: pendientes. La declaración deberá actualizarse al disponer de resultados y barreras identificadas.</p>
          </div>
        </div>
      </div>
    </section>

    <section class="seccion-verde-claro">
      <div class="contenedor dos-col-equilibrado">
        <div>
          <p class="etiqueta">Tu experiencia nos orienta</p>
          <h2>Ayúdanos a reconocer las barreras.</h2>
          <p class="descripcion" style="color: var(--texto); opacity: 0.85;">
            Describe qué intentabas hacer y qué te lo impidió. Puedes mencionar el dispositivo, el navegador o la tecnología de asistencia, sin compartir diagnósticos ni información sensible.
          </p>
          <div style="width: 40px; height: 1px; background: var(--texto); opacity: 0.3; margin: 22px 0;"></div>
          <strong style="font-size: 12.5px; display: block; margin-bottom: 8px;">Otra forma de compartir tu experiencia</strong>
          <strong style="font-size: 13px; display: block; margin-bottom: 10px;">orientacion@savia.example</strong>
          <p style="font-size: 11.5px; color: var(--texto); opacity: 0.8;">
            Asunto sugerido: Accesibilidad. Contacto ilustrativo; no recibe mensajes reales. En la versión operativa se deberá ofrecer seguimiento por un canal accesible acordado contigo.
          </p>
        </div>

        <form class="formulario-caja" onsubmit="mostrarMensajeExito(event, 'exito-accesibilidad')">
          <h3 style="font-size: 26px; margin-bottom: 18px;">Comparte una mejora</h3>

          <div class="campo">
            <label for="acc-contacto">Contacto (opcional)</label>
            <input type="email" id="acc-contacto" placeholder="Tu correo electrónico">
            <small>Solo si deseas recibir seguimiento a tu comentario.</small>
          </div>

          <div class="campo">
            <label for="acc-pagina">Página afectada</label>
            <input type="text" id="acc-pagina" placeholder="Nombre de la página o dirección" required>
            <small>Por ejemplo: Solicitar información. Campo necesario.</small>
          </div>

          <div class="campo">
            <label for="acc-desc">Descripción de la barrera</label>
            <textarea id="acc-desc" placeholder="Cuéntanos qué ocurrió y qué necesitabas hacer." required></textarea>
            <small>Campo necesario. Evita incluir datos personales de otras personas.</small>
          </div>

          <p style="font-size: 11px; color: var(--gris); margin-bottom: 18px;">
            Los datos se utilizarían únicamente para revisar la barrera y responder, si incluyes un contacto. Consulta el documento de Privacidad antes de enviar información en una versión operativa.
          </p>

          <button type="submit" class="boton">Enviar comentario de accesibilidad</button>

          <strong style="font-size: 10.5px; display: block; margin-top: 16px;">
            Formulario de muestra: no recopila ni envía datos.
          </strong>

          <div id="exito-accesibilidad" class="mensaje-exito">
            ✓ Comentario de accesibilidad registrado de forma ilustrativa. Gracias por ayudarnos a mejorar.
          </div>
        </form>
      </div>
    </section>
  </main>

  <!-- =========================================================
       PIE DE PÁGINA COMÚN
       ========================================================= -->
  <footer>
    <div class="contenedor">
      <div class="footer-grid">
        <div>
          <div class="logo" onclick="mostrarVista('inicio', event)">
            <svg class="logo-icono" viewBox="0 0 40 40" fill="none">
              <circle cx="20" cy="20" r="18.5" stroke="currentColor" stroke-width="1.2"/>
              <path d="M18 19C14.5 19 12 16.5 12 13.5C15.5 13.5 18 15.5 18 19Z" stroke="currentColor" stroke-width="1.2"/>
              <path d="M21 21C24.5 21 28 18 28 14C24 14 21 16.5 21 21Z" stroke="currentColor" stroke-width="1.2"/>
            </svg>
            <div class="logo-texto">
              savia
              <small>Psicología y ciencias humanas</small>
            </div>
          </div>
          <p style="margin-top: 16px;">
            Formación en psicología y ciencias humanas para comprender, acompañar y transformar.
          </p>
        </div>

        <div>
          <h4>Explora Savia</h4>
          <a href="#inicio" onclick="mostrarVista('inicio', event)">Inicio</a>
          <a href="#programa" onclick="mostrarVista('programa', event)">Conoce el programa</a>
          <a href="#especialidades" onclick="mostrarVista('especialidades', event)">Especialidades</a>
          <a href="#nosotros" onclick="mostrarVista('nosotros', event)">Nosotros</a>
          <a href="#inscribirme" onclick="mostrarVista('inscribirme', event)">Inscribirme</a>
          <a href="#faq" onclick="mostrarVista('faq', event)">Preguntas frecuentes</a>
          <a href="#solicitar-info" onclick="mostrarVista('solicitar-info', event)">Solicitar información</a>
        </div>

        <div>
          <h4>Orientación para aspirantes</h4>
          <a href="mailto:orientacion@savia.example">orientacion@savia.example</a>
          <p style="margin-top: 8px;">Lunes a viernes<br>&nbsp;&nbsp;09:00–18:00 h</p>
          <p style="font-size: 10px; margin-top: 10px;">
            Información ilustrativa · Correo y horario de ejemplo.
          </p>
        </div>

        <div>
          <h4>Una propuesta conceptual</h4>
          <p>
            Información ilustrativa. Savia es una identidad académica conceptual. Fechas, costos,
            trayectoria y perfiles no corresponden a una institución real.
          </p>
        </div>
      </div>

      <div class="footer-final">
        <span>© 2026 Savia · Psicología y ciencias humanas</span>
        <div class="footer-links-legal">
          <a href="#privacidad" onclick="mostrarVista('privacidad', event)">Privacidad</a>
          <a href="#accesibilidad" onclick="mostrarVista('accesibilidad', event)">Accesibilidad</a>
        </div>
      </div>
    </div>
  </footer>

  <!-- JAVASCRIPT -->
  <script>
    let especialidadSeleccionada = 'Clínica';

    function mostrarVista(nombreVista, evento) {
      if (evento) evento.preventDefault();

      document.querySelectorAll('.vista').forEach(v => v.classList.remove('activa'));

      const vistaActiva = document.getElementById('vista-' + nombreVista);
      if (vistaActiva) vistaActiva.classList.add('activa');

      document.querySelectorAll('nav a').forEach(link => link.classList.remove('nav-activo'));
      const navActivo = document.getElementById('nav-' + nombreVista);
      if (navActivo && nombreVista !== 'inscribirme') {
        navActivo.classList.add('nav-activo');
      }

      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function irAMiRuta(evento) {
      if (evento) evento.preventDefault();
      mostrarVista('inicio', null);
      setTimeout(() => {
        const seccion = document.getElementById('mi-ruta-preview');
        if (seccion) seccion.scrollIntoView({ behavior: 'smooth' });
      }, 60);
    }

    function elegirEspecialidadPreview(nombreEsp, boton) {
      especialidadSeleccionada = nombreEsp;
      document.querySelectorAll('.chip-esp').forEach(c => c.classList.remove('activo'));
      boton.classList.add('activo');
      actualizarVistaPrevia();
    }

    function actualizarVistaPrevia() {
      const nombre = document.getElementById('prev-nombre').value.trim();
      const correo = document.getElementById('prev-correo').value.trim();
      const modalidad = document.getElementById('prev-modalidad').value;
      const nota = document.getElementById('prev-nota').value.trim();

      document.getElementById('out-nombre').textContent = nombre || 'Sin especificar';
      document.getElementById('out-correo').textContent = correo || 'aspirante@ejemplo.com';
      document.getElementById('out-esp').textContent = especialidadSeleccionada;
      document.getElementById('out-mod').textContent = modalidad;
      document.getElementById('out-nota').textContent = nota || 'Ninguna nota agregada';
    }

    function simularVistaPrevia() {
      actualizarVistaPrevia();
      document.getElementById('feedback-preview').style.display = 'block';
    }

    function toggleAcordeon(boton) {
      const item = boton.parentElement;
      const signo = boton.querySelector('.acordeon-signo');
      const estaAbierto = item.classList.contains('abierto');

      item.classList.toggle('abierto');
      signo.textContent = estaAbierto ? '+' : '−';
    }

    function filtrarFaq(categoria, boton) {
      document.querySelectorAll('.faq-tab').forEach(t => t.classList.remove('activa'));
      boton.classList.add('activa');

      document.querySelectorAll('.faq-bloque').forEach(bloque => {
        if (categoria === 'todas' || bloque.dataset.cat === categoria) {
          bloque.style.display = 'grid';
        } else {
          bloque.style.display = 'none';
        }
      });
    }

    function seleccionarHorario(boton) {
      document.querySelectorAll('.btn-horario').forEach(b => b.classList.remove('seleccionado'));
      boton.classList.add('seleccionado');
    }

    function cambiarContraste(activarAlto) {
      const dotEstandar = document.getElementById('dot-estandar');
      const dotAlto = document.getElementById('dot-alto');

      if (activarAlto) {
        document.body.classList.add('alto-contraste');
        dotEstandar.textContent = '○';
        dotAlto.textContent = '●';
      } else {
        document.body.classList.remove('alto-contraste');
        dotEstandar.textContent = '●';
        dotAlto.textContent = '○';
      }
    }

    function actualizarArchivo(input) {
      if (input.files && input.files[0]) {
        const preview = document.getElementById('archivo-preview');
        const nombre = document.getElementById('nombre-archivo');
        nombre.textContent = input.files[0].name;
        preview.style.display = 'flex';
      }
    }

    function mostrarMensajeExito(evento, idMensaje) {
      evento.preventDefault();
      document.getElementById(idMensaje).style.display = 'block';
    }
  </script>

</body>
</html>
