---
layout: page
title: Busco a las primeras personas con quienes construir esta experiencia
permalink: /cursos/autoconocimiento
comments: false
image: assets/images/Portada-Curso-astrologia-Autoconocimiento.jpg
imageshadow: true
---

'use client';

import React, { useState, useEffect, useRef } from 'react';

function useIntersectionObserver(threshold = 0.15) {
  const ref = useRef<HTMLDivElement>(null);
  const [isVisible, setIsVisible] = useState(false);

  useEffect(() => {
    const observer = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting) {
          setIsVisible(true);
          observer.disconnect();
        }
      },
      { threshold }
    );
    if (ref.current) observer.observe(ref.current);
    return () => observer.disconnect();
  }, [threshold]);

  return { ref, isVisible };
}

const GOOGLE_FORMS_URL = 'https://forms.gle/YOUR_GOOGLE_FORM_ID';

export default function LaboratorioPage() {
  const [isScrolled, setIsScrolled] = useState(false);

  const heroSection = useIntersectionObserver();
  const invitacionSection = useIntersectionObserver();
  const queEsSection = useIntersectionObserver();
  const experienciaSection = useIntersectionObserver();
  const ciudadesSection = useIntersectionObserver();
  const convocatoriaSection = useIntersectionObserver();
  const formSection = useIntersectionObserver();

  useEffect(() => {
    const handleScroll = () => setIsScrolled(window.scrollY > 60);
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const experiencias = [
  { icon: '✦', label: 'Astrología' },
  { icon: '✦', label: 'Conversación' },
  { icon: '✦', label: 'Escritura' },
  { icon: '✦', label: 'Arte' },
  { icon: '✦', label: 'Meditación' },
  { icon: '✦', label: 'Naturaleza' },
  { icon: '✦', label: 'Ejercicios simbólicos' },
  { icon: '✦', label: 'Té, café y buenas conversaciones' }];


  const beneficios = [
  'Conocer antes que nadie la fecha de apertura.',
  'Recibir toda la información del primer laboratorio.',
  'Participar en esta etapa de construcción.',
  'Acceder a beneficios exclusivos para quienes hagan parte de la primera generación.'];


  const resonancias = [
  'Sientes que la vida va demasiado rápido y hace tiempo no encuentras un espacio para detenerte.',
  'Estás viviendo un cambio importante y buscas una nueva manera de comprender lo que te sucede.',
  'Te interesa la astrología, pero buscas algo más profundo que aprender signos o leer horóscopos.',
  'Extrañas conversaciones con personas que también disfrutan hacer preguntas, explorar ideas y aprender juntas.',
  'Quisieras desarrollar una nueva mirada sobre ti, sobre los demás y sobre el momento histórico que estamos viviendo.'];


  return (
    <div className="min-h-screen bg-white" style={{ fontFamily: "'Dosis', 'Sen', sans-serif" }}>
      {/* Global Styles */}
      <style>{`
        @font-face {
          font-family: 'aristotelica';
          font-weight: 700;
          src: local('Georgia Bold');
        }
        .font-heading {
          font-family: 'aristotelica', 'Georgia', 'Times New Roman', serif;
        }
        .font-body {
          font-family: 'Dosis', 'Sen', sans-serif;
        }
        .btn-astro {
          background-color: #bd8762;
          color: #212529;
          border: 1px solid #000000;
          padding: 10px 30px;
          border-radius: 5px;
          font-family: 'Dosis', 'Sen', sans-serif;
          font-size: 18px;
          font-weight: 600;
          cursor: pointer;
          display: inline-block;
          text-decoration: none;
          transition: background-color 0.2s ease, transform 0.15s ease, box-shadow 0.2s ease;
          letter-spacing: 0.02em;
        }
        .btn-astro:hover {
          background-color: #a06b45;
          transform: translateY(-2px);
          box-shadow: 0 4px 12px rgba(189,135,98,0.35);
        }
        .btn-astro:active {
          transform: translateY(0);
        }
        .btn-astro-outline {
          background-color: transparent;
          color: #212529;
          border: 1px solid #212529;
          padding: 10px 30px;
          border-radius: 5px;
          font-family: 'Dosis', 'Sen', sans-serif;
          font-size: 18px;
          font-weight: 600;
          cursor: pointer;
          display: inline-block;
          text-decoration: none;
          transition: all 0.2s ease;
        }
        .btn-astro-outline:hover {
          background-color: #212529;
          color: #ffffff;
        }
        .article-post p {
          font-size: 22px;
          line-height: 37.4px;
          margin-bottom: 1.2rem;
          color: #212529;
        }
        .posttitle {
          font-family: 'aristotelica', 'Georgia', serif;
          font-size: 50px;
          line-height: 60px;
          font-weight: 700;
          color: #212529;
          text-transform: uppercase;
          margin-bottom: 8px;
        }
        @media (max-width: 768px) {
          .posttitle {
            font-size: 32px;
            line-height: 40px;
          }
        }
        .main-banner {
          height: 400px;
          background-size: cover;
          background-position: center;
          background-repeat: no-repeat;
        }
        .site-content {
          margin-left: 80px;
        }
        @media (max-width: 768px) {
          .site-content {
            margin-left: 0;
          }
        }
        .sidebar-fixed {
          position: fixed;
          left: 0;
          top: 0;
          width: 80px;
          height: 100vh;
          background: #ffffff;
          border-right: 1px solid #f0ebe3;
          z-index: 100;
          display: flex;
          flex-direction: column;
          align-items: center;
          padding-top: 20px;
        }
        @media (max-width: 768px) {
          .sidebar-fixed {
            display: none;
          }
        }
        .social-icons-fixed {
          position: fixed;
          left: 26px;
          top: 50%;
          transform: translateY(-50%);
          z-index: 101;
          display: flex;
          flex-direction: column;
          gap: 16px;
        }
        @media (max-width: 768px) {
          .social-icons-fixed {
            display: none;
          }
        }
        .social-icon-link {
          color: #111111;
          font-size: 18px;
          transition: color 0.2s ease, transform 0.2s ease;
          display: flex;
          align-items: center;
          justify-content: center;
          width: 28px;
          height: 28px;
        }
        .social-icon-link:hover {
          color: #bd8762;
          transform: scale(1.2);
        }
        .navbar-top {
          background: #ffffff;
          border-bottom: 1px solid #f0ebe3;
          padding: 8px 16px;
          display: flex;
          align-items: center;
          justify-content: space-between;
        }
        .navbar-motto {
          font-family: 'Dosis', 'Sen', sans-serif;
          font-size: 14px;
          color: #212529;
          text-align: right;
          text-transform: uppercase;
          letter-spacing: 0.05em;
        }
        .navbar-motto strong {
          font-weight: 700;
        }
        .container-main {
          max-width: 80%;
          margin: 0 auto;
          padding: 0 16px;
        }
        @media (max-width: 1024px) {
          .container-main {
            max-width: 95%;
          }
        }
        .article-post {
          max-width: 1000px;
          padding: 0 20px;
        }
        .resonancia-item {
          padding: 16px 0;
          border-bottom: 1px solid #f0ebe3;
          font-size: 22px;
          line-height: 37.4px;
          color: #212529;
          transition: color 0.2s ease;
        }
        .resonancia-item:hover {
          color: #bd8762;
        }
        .resonancia-item::before {
          content: '…';
          color: #bd8762;
          font-weight: 700;
          margin-right: 4px;
        }
        .experiencia-tag {
          display: inline-flex;
          align-items: center;
          gap: 8px;
          padding: 8px 20px;
          border: 1px solid #212529;
          border-radius: 100px;
          font-size: 18px;
          font-family: 'Dosis', 'Sen', sans-serif;
          color: #212529;
          margin: 4px;
          transition: all 0.2s ease;
          background: #ffffff;
        }
        .experiencia-tag:hover {
          background: #bd8762;
          border-color: #bd8762;
          color: #ffffff;
          transform: translateY(-2px);
        }
        .ciudad-card {
          border: 1px solid #e0d8cc;
          border-radius: 8px;
          padding: 32px;
          background: #f8f5f0;
          transition: box-shadow 0.2s ease, transform 0.2s ease;
        }
        .ciudad-card:hover {
          box-shadow: 0 8px 24px rgba(0,0,0,0.08);
          transform: translateY(-4px);
        }
        .form-input {
          width: 100%;
          padding: 12px 16px;
          border: 1px solid #212529;
          border-radius: 5px;
          font-family: 'Dosis', 'Sen', sans-serif;
          font-size: 18px;
          color: #212529;
          background: #ffffff;
          outline: none;
          transition: border-color 0.2s ease, box-shadow 0.2s ease;
        }
        .form-input:focus {
          border-color: #bd8762;
          box-shadow: 0 0 0 3px rgba(189,135,98,0.15);
        }
        .form-input.error {
          border-color: #dc3545;
        }
        .form-label {
          display: block;
          font-family: 'Dosis', 'Sen', sans-serif;
          font-size: 14px;
          font-weight: 600;
          color: #212529;
          margin-bottom: 6px;
          text-transform: uppercase;
          letter-spacing: 0.05em;
        }
        .error-msg {
          color: #dc3545;
          font-size: 14px;
          margin-top: 4px;
        }
        .blockquote-astro {
          border-left: 4px solid #bd8762;
          padding: 16px 24px;
          margin: 24px 0;
          background: #f8f5f0;
          font-style: italic;
          font-size: 22px;
          line-height: 37.4px;
          color: #212529;
        }
        .newsletter-section {
          background: #f8f5f0;
          border-top: 1px solid #e0d8cc;
          padding: 48px 16px;
          text-align: center;
        }
        .footer-bar {
          background: #ffffff;
          border-top: 1px solid #e0d8cc;
          padding: 20px 16px;
          font-size: 14px;
          color: #6c757d;
        }
        .fade-in-up {
          opacity: 0;
          transform: translateY(30px);
          transition: opacity 0.7s ease-out, transform 0.7s ease-out;
        }
        .fade-in-up.visible {
          opacity: 1;
          transform: translateY(0);
        }
        .fade-in {
          opacity: 0;
          transition: opacity 0.6s ease-out;
        }
        .fade-in.visible {
          opacity: 1;
        }
        .sticky-cta {
          position: fixed;
          bottom: 24px;
          right: 24px;
          z-index: 200;
          transition: opacity 0.3s ease, transform 0.3s ease;
        }
        .sticky-cta.hidden {
          opacity: 0;
          transform: translateY(20px);
          pointer-events: none;
        }
        .sticky-cta.visible {
          opacity: 1;
          transform: translateY(0);
        }
        .section-divider {
          width: 60px;
          height: 2px;
          background: #bd8762;
          margin: 16px 0 24px 0;
        }
        .highlight-text {
          color: #bd8762;
          font-weight: 700;
        }
        .beneficio-item {
          display: flex;
          align-items: flex-start;
          gap: 12px;
          padding: 12px 0;
          font-size: 20px;
          line-height: 32px;
          color: #212529;
          border-bottom: 1px solid #f0ebe3;
        }
        .beneficio-item:last-child {
          border-bottom: none;
        }
        .beneficio-check {
          color: #bd8762;
          font-size: 20px;
          flex-shrink: 0;
          margin-top: 4px;
        }
        .form-section-bg {
          background: linear-gradient(135deg, #f8f5f0 0%, #ffffff 100%);
          border-top: 3px solid #bd8762;
        }
        .logo-circle {
          width: 60px;
          height: 60px;
          border-radius: 50%;
          border: 2px solid #212529;
          display: flex;
          align-items: center;
          justify-content: center;
          font-family: 'aristotelica', 'Georgia', serif;
          font-size: 10px;
          font-weight: 700;
          text-align: center;
          color: #212529;
          letter-spacing: 0.1em;
          text-transform: uppercase;
          line-height: 1.2;
          padding: 4px;
        }
        .section-heading {
          font-family: 'aristotelica', 'Georgia', serif;
          font-size: 28px;
          font-weight: 700;
          color: #212529;
          text-transform: uppercase;
          letter-spacing: 0.03em;
          margin-bottom: 8px;
        }
        @media (max-width: 768px) {
          .section-heading {
            font-size: 22px;
          }
        }
        .progress-bar {
          position: fixed;
          top: 0;
          left: 0;
          height: 3px;
          background: #bd8762;
          z-index: 999;
          transition: width 0.1s linear;
        }
        .image-float-right {
          float: right;
          width: 40%;
          padding: 0 0 0 4em;
          border-radius: 4px;
        }
        @media (max-width: 768px) {
          .image-float-right {
            float: none;
            width: 100%;
            padding: 0;
            margin-bottom: 24px;
          }
        }
      `}</style>

      {/* Progress Bar */}
      <ScrollProgressBar />

      {/* Sidebar */}
      <div className="sidebar-fixed" />

      {/* Fixed Social Icons */}
      <div className="social-icons-fixed">
        <a href="https://instagram.com/astrologia.social" target="_blank" rel="noopener noreferrer" className="social-icon-link" aria-label="Instagram">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z" />
          </svg>
        </a>
        <a href="https://www.facebook.com/astrologia.social.latam" target="_blank" rel="noopener noreferrer" className="social-icon-link" aria-label="Facebook">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
            <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z" />
          </svg>
        </a>
        <a href="https://wa.me/5492921435720" target="_blank" rel="noopener noreferrer" className="social-icon-link" aria-label="WhatsApp">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z" />
          </svg>
        </a>
      </div>

      {/* Main Site Content */}
      <div className="site-content">

        {/* Navbar */}
        <div className="navbar-top container-main">
          <div className="flex items-center gap-4">
            <div className="logo-circle">
              <span style={{ fontSize: '7px', letterSpacing: '0.08em', textAlign: 'center', lineHeight: '1.1' }}>ASTROLOGÍA<br />SOCIAL</span>
            </div>
          </div>
          <div className="navbar-motto">
            <strong>Nos movemos juntxs</strong> en un universo de posibilidades
          </div>
        </div>

        {/* Hero Banner */}
        <div
          className="main-banner"
          style={{
            backgroundImage: `url('https://images.unsplash.com/photo-1519681393784-d120267933ba?w=1400&q=80')`,
            backgroundSize: 'cover',
            backgroundPosition: 'center top'
          }}>
          
          <div style={{
            width: '100%',
            height: '100%',
            background: 'linear-gradient(to bottom, rgba(0,0,0,0.15) 0%, rgba(0,0,0,0.4) 100%)',
            display: 'flex',
            alignItems: 'flex-end',
            padding: '32px'
          }}>
            <div>
              <span style={{
                background: '#bd8762',
                color: '#ffffff',
                padding: '4px 16px',
                borderRadius: '3px',
                fontSize: '14px',
                fontFamily: "'Dosis', 'Sen', sans-serif",
                fontWeight: 600,
                letterSpacing: '0.1em',
                textTransform: 'uppercase'
              }}>Primera Experiencia</span>
              <h2 style={{
                fontFamily: "'aristotelica', 'Georgia', serif",
                fontSize: '36px',
                fontWeight: 700,
                color: '#ffffff',
                marginTop: '8px',
                textShadow: '0 2px 8px rgba(0,0,0,0.4)',
                textTransform: 'uppercase'
              }}>Laboratorio Astrológico<br />y Simbólico</h2>
              <p style={{
                color: 'rgba(255,255,255,0.9)',
                fontSize: '18px',
                fontFamily: "'Dosis', 'Sen', sans-serif",
                marginTop: '4px'
              }}>Lenguaje y Símbolos Astrológicos &mdash; Cinco encuentros presenciales</p>
            </div>
          </div>
        </div>

        {/* Main Content */}
        <div className="container-main">

          {/* Page Title */}
          <div className="page-single" style={{ paddingTop: '32px', paddingBottom: '16px' }}>
            <div className="entry-header">
              <h1 className="posttitle">Laboratorio Astrológico y Simbólico</h1>
              <p style={{
                fontFamily: "'Dosis', 'Sen', sans-serif",
                fontSize: '22px',
                color: '#6c757d',
                marginTop: '8px',
                marginBottom: '0'
              }}>Una experiencia para quienes sienten que la vida necesita ser vivida con más sentido.</p>
            </div>
          </div>

          {/* Article Content */}
          <div className="article-post">

            {/* Intro + Image */}
            <div
              ref={heroSection.ref}
              className={`fade-in-up ${heroSection.isVisible ? 'visible' : ''}`}>
              
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Vivimos en una época que nos mantiene ocupados, conectados y en movimiento.
              </p>
              <img
                src="https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=600&q=80"
                alt="Cuaderno con notas astrológicas y mapas celestes sobre una mesa de madera"
                className="image-float-right"
                style={{ borderRadius: '4px' }} />
              
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Pero pocas veces nos deja tiempo para detenernos, mirar nuestra vida con perspectiva y preguntarnos quiénes estamos siendo.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Quizá por eso muchas personas sienten que algo cambió por dentro, aunque todavía no sepan ponerle nombre.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Este laboratorio nace para abrir ese espacio.
              </p>
            </div>

            {/* Tal vez este espacio es para ti */}
            <div
              ref={invitacionSection.ref}
              className={`fade-in-up ${invitacionSection.isVisible ? 'visible' : ''}`}
              style={{ marginTop: '40px' }}>
              
              <h2 className="section-heading">Tal vez este espacio es para ti si…</h2>
              <div className="section-divider" />
              <div>
                {resonancias.map((item, i) =>
                <div key={i} className="resonancia-item">
                    {item}
                  </div>
                )}
              </div>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginTop: '24px', color: '#212529', fontStyle: 'italic' }}>
                Si alguna de estas frases ressonó contigo, quizá este laboratorio también lo haga.
              </p>
            </div>

            {/* Qué es */}
            <div
              ref={queEsSection.ref}
              className={`fade-in-up ${queEsSection.isVisible ? 'visible' : ''}`}
              style={{ marginTop: '48px' }}>
              
              <h2 className="section-heading">¿Qué es el Laboratorio Astrológico y Simbólico?</h2>
              <div className="section-divider" />
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                No es una escuela tradicional.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                No es un curso para memorizar conceptos.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Es un círculo presencial para aprender a leer la vida a través del lenguaje de la astrología, compartir con otras personas y recuperar el placer de pensar, crear y conversar.
              </p>
              <div className="blockquote-astro">
                &ldquo;Un círculo presencial donde exploraremos la astrología como un lenguaje vivo: un puente entre el cielo, la naturaleza y la experiencia humana.&rdquo;
              </div>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Aquí la astrología no será únicamente un conocimiento que estudiar, sino una herramienta para observar, hacer preguntas y descubrir nuevas formas de relacionarnos con nosotros mismos, con los demás y con el tiempo que habitamos.
              </p>
            </div>

            {/* Por qué la astrología */}
            <div
              style={{ marginTop: '48px', background: '#f8f5f0', padding: '32px', borderRadius: '8px', borderLeft: '4px solid #bd8762' }}
              className={`fade-in-up ${queEsSection.isVisible ? 'visible' : ''}`}>
              
              <h2 className="section-heading">¿Por qué la astrología?</h2>
              <div className="section-divider" />
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Porque la astrología no es solamente un conjunto de conocimientos.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Es un <strong>lenguaje</strong>.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Un lenguaje que nos permite reconocer patrones, comprender los ritmos de la vida y hacer visible aquello que normalmente permanece oculto.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Nos recuerda que no somos individuos aislados, sino parte de sistemas más amplios: una familia, una cultura, una comunidad, la naturaleza y el tiempo que habitamos.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '0', color: '#212529' }}>
                Cuando cambia la forma en que interpretamos la realidad, también cambia la forma en que la vivimos.
              </p>
            </div>

            {/* Qué encontrarás */}
            <div
              ref={experienciaSection.ref}
              className={`fade-in-up ${experienciaSection.isVisible ? 'visible' : ''}`}
              style={{ marginTop: '48px' }}>
              
              <h2 className="section-heading">¿Qué encontrarás?</h2>
              <div className="section-divider" />
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '24px', color: '#212529' }}>
                Cada encuentro combina diferentes formas de explorar el lenguaje simbólico:
              </p>
              <div style={{ display: 'flex', flexWrap: 'wrap', gap: '8px', marginBottom: '32px' }}>
                {experiencias.map((exp, i) =>
                <span key={i} className="experiencia-tag">
                    <span style={{ color: '#bd8762' }}>{exp.icon}</span>
                    {exp.label}
                  </span>
                )}
              </div>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Mi intención es que cada encuentro sea un refugio en medio de la rutina.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Un lugar donde aprender, sorprenderte, construir comunidad y volver a mirar la vida con curiosidad.
              </p>
            </div>

            {/* Primera Experiencia */}
            <div
              style={{ marginTop: '48px', background: '#212529', color: '#ffffff', padding: '40px 32px', borderRadius: '8px' }}
              className={`fade-in-up ${experienciaSection.isVisible ? 'visible' : ''}`}>
              
              <p style={{ fontSize: '14px', letterSpacing: '0.15em', textTransform: 'uppercase', color: '#bd8762', fontWeight: 600, marginBottom: '8px' }}>Primera Experiencia</p>
              <h2 style={{ fontFamily: "'aristotelica', 'Georgia', serif", fontSize: '28px', fontWeight: 700, color: '#ffffff', textTransform: 'uppercase', marginBottom: '16px' }}>Lenguaje y Símbolos Astrológicos</h2>
              <p style={{ fontSize: '20px', lineHeight: '34px', color: 'rgba(255,255,255,0.85)', marginBottom: '16px' }}>
                Cinco encuentros presenciales para descubrir las bases del lenguaje astrológico y comenzar a leer la realidad desde una perspectiva completamente nueva.
              </p>
              <p style={{ fontSize: '20px', lineHeight: '34px', color: 'rgba(255,255,255,0.85)', marginBottom: '0' }}>
                No necesitas conocimientos previos. Solo curiosidad y el deseo de vivir una experiencia diferente.
              </p>
            </div>

            {/* Ciudades */}
            <div
              ref={ciudadesSection.ref}
              className={`fade-in-up ${ciudadesSection.isVisible ? 'visible' : ''}`}
              style={{ marginTop: '48px' }}>
              
              <h2 className="section-heading">Dos ciudades</h2>
              <div className="section-divider" />
              <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(280px, 1fr))', gap: '24px', marginTop: '8px' }}>
                <div className="ciudad-card">
                  <div style={{ display: 'flex', alignItems: 'center', gap: '12px', marginBottom: '16px' }}>
                    <span style={{ fontSize: '28px' }}>🌿</span>
                    <h3 style={{ fontFamily: "'aristotelica', 'Georgia', serif", fontSize: '22px', fontWeight: 700, color: '#212529', textTransform: 'uppercase', margin: 0 }}>San Francisco</h3>
                  </div>
                  <p style={{ fontSize: '14px', color: '#6c757d', marginBottom: '12px', textTransform: 'uppercase', letterSpacing: '0.08em' }}>Cundinamarca</p>
                  <p style={{ fontSize: '18px', lineHeight: '30px', color: '#212529', margin: 0 }}>
                    Un círculo en contacto con la naturaleza para quienes desean aprender con calma y construir comunidad.
                  </p>
                </div>
                <div className="ciudad-card">
                  <div style={{ display: 'flex', alignItems: 'center', gap: '12px', marginBottom: '16px' }}>
                    <span style={{ fontSize: '28px' }}>🏙️</span>
                    <h3 style={{ fontFamily: "'aristotelica', 'Georgia', serif", fontSize: '22px', fontWeight: 700, color: '#212529', textTransform: 'uppercase', margin: 0 }}>Bogotá</h3>
                  </div>
                  <p style={{ fontSize: '14px', color: '#6c757d', marginBottom: '12px', textTransform: 'uppercase', letterSpacing: '0.08em' }}>Colombia</p>
                  <p style={{ fontSize: '18px', lineHeight: '30px', color: '#212529', margin: 0 }}>
                    Un espacio para hacer una pausa en medio del ritmo de la ciudad, aprender en compañía y encontrarte con personas afines.
                  </p>
                </div>
              </div>
            </div>

            {/* Convocatoria */}
            <div
              ref={convocatoriaSection.ref}
              className={`fade-in-up ${convocatoriaSection.isVisible ? 'visible' : ''}`}
              style={{ marginTop: '48px' }}>
              
              <img
                src="https://images.unsplash.com/photo-1444703686981-a3abbc4d4fe3?w=600&q=80"
                alt="Mapa estelar y cartas astrológicas sobre una mesa con notas y lápices"
                className="image-float-right"
                style={{ borderRadius: '4px' }} />
              
              <h2 className="section-heading">Esta es una convocatoria</h2>
              <div className="section-divider" />
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Estoy buscando a las primeras personas que quieran formar parte del Laboratorio Astrológico y Simbólico.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Quiero construir esta experiencia junto a un grupo pequeño, curioso y dispuesto a explorar nuevas formas de comprender la vida.
              </p>
              <p style={{ fontSize: '22px', lineHeight: '37.4px', marginBottom: '1.2rem', color: '#212529' }}>
                Si sientes que este puede ser tu lugar, me encantará conocerte.
              </p>
              <p style={{ fontSize: '18px', lineHeight: '30px', marginBottom: '24px', color: '#6c757d', fontStyle: 'italic' }}>
                Responder este formulario no representa ningún compromiso.
              </p>
              <p style={{ fontSize: '20px', lineHeight: '34px', marginBottom: '16px', color: '#212529', fontWeight: 600 }}>
                Simplemente te permitirá:
              </p>
              <div style={{ marginBottom: '32px' }}>
                {beneficios.map((b, i) =>
                <div key={i} className="beneficio-item">
                    <span className="beneficio-check">✓</span>
                    <span>{b}</span>
                  </div>
                )}
              </div>
              <button onClick={() => window.location.href = GOOGLE_FORMS_URL} className="btn-astro">
                Quiero saber más →
              </button>
            </div>

          </div>{/* end article-post */}
        </div>{/* end container-main */}

        {/* CTA Section */}
        <div
          id="formulario"
          ref={formSection.ref}
          className={`form-section-bg fade-in ${formSection.isVisible ? 'visible' : ''}`}
          style={{ marginTop: '64px', padding: '80px 0' }}>
          
          <div className="container-main">
            <div style={{ maxWidth: '640px', margin: '0 auto', textAlign: 'center' }}>
              <p style={{ fontSize: '14px', letterSpacing: '0.15em', textTransform: 'uppercase', color: '#bd8762', fontWeight: 600, marginBottom: '8px', fontFamily: "'Dosis', 'Sen', sans-serif" }}>Quiero saber más</p>
              <h2 style={{ fontFamily: "'aristotelica', 'Georgia', serif", fontSize: '36px', fontWeight: 700, color: '#212529', textTransform: 'uppercase', marginBottom: '16px', lineHeight: '44px' }}>
                Únete al Laboratorio
              </h2>
              <p style={{ fontSize: '20px', lineHeight: '34px', color: '#212529', marginBottom: '8px' }}>
                Cuéntame un poco sobre ti y recibirás toda la información sobre las primeras fechas, ciudades y beneficios para quienes hagan parte de esta primera generación.
              </p>
              <p style={{ fontSize: '18px', lineHeight: '30px', color: '#6c757d', marginBottom: '40px', fontStyle: 'italic' }}>
                Será un gusto conocerte.
              </p>
              <a
                href={GOOGLE_FORMS_URL}
                target="_blank"
                rel="noopener noreferrer"
                className="btn-astro"
                style={{ fontSize: '20px', padding: '16px 48px', display: 'inline-block' }}>
                Quiero ser parte →
              </a>
              <p style={{ fontSize: '14px', color: '#6c757d', marginTop: '16px' }}>
                Completar el formulario no representa ningún compromiso económico.
              </p>
            </div>
          </div>
        </div>

        {/* Astrología Social Closing */}
        <div style={{ background: '#212529', padding: '48px 0', textAlign: 'center' }}>
          <div className="container-main">
            <div className="logo-circle" style={{ margin: '0 auto 16px', borderColor: '#bd8762', color: '#ffffff' }}>
              <span style={{ fontSize: '7px', letterSpacing: '0.08em', textAlign: 'center', lineHeight: '1.1', color: '#ffffff' }}>ASTROLOGÍA<br />SOCIAL</span>
            </div>
            <h3 style={{ fontFamily: "'aristotelica', 'Georgia', serif", fontSize: '24px', fontWeight: 700, color: '#ffffff', textTransform: 'uppercase', marginBottom: '12px' }}>Astrología Social</h3>
            <p style={{ fontSize: '18px', color: 'rgba(255,255,255,0.7)', maxWidth: '500px', margin: '0 auto 24px', lineHeight: '30px' }}>
              Aprender a leer el cielo para habitar la Tierra con más conciencia.
            </p>
            <button onClick={() => window.location.href = GOOGLE_FORMS_URL} className="btn-astro">
              Quiero ser parte →
            </button>
          </div>
        </div>

        {/* Newsletter */}
        <div className="newsletter-section">
          <div className="container-main">
            <div style={{ display: 'flex', alignItems: 'center', justifyContent: 'center', gap: '12px', marginBottom: '24px', flexWrap: 'wrap' }}>
              <div className="logo-circle" style={{ width: '40px', height: '40px', flexShrink: 0 }}>
                <span style={{ fontSize: '5px', letterSpacing: '0.06em', textAlign: 'center', lineHeight: '1.1' }}>AS</span>
              </div>
              <span style={{ fontSize: '18px', fontFamily: "'Dosis', 'Sen', sans-serif", color: '#212529' }}>
                No te pierdas nuestras novedades, <strong>suscríbete a nuestro Newsletter.</strong>
              </span>
            </div>
            <NewsletterForm />
          </div>
        </div>

        {/* Footer */}
        <footer className="footer-bar">
          <div className="container-main">
            <div style={{ display: 'flex', justifyContent: 'space-between', flexWrap: 'wrap', gap: '8px' }}>
              <span>Copyleft &copy; 2026 Astrologia Social</span>
              <span>Hecho con amor para quienes buscan vivir con más sentido.</span>
            </div>
          </div>
        </footer>

      </div>{/* end site-content */}

      {/* Sticky CTA */}
      <div className={`sticky-cta ${isScrolled ? 'visible' : 'hidden'}`}>
        <button onClick={() => window.location.href = GOOGLE_FORMS_URL} className="btn-astro" style={{ boxShadow: '0 4px 20px rgba(0,0,0,0.2)' }}>
          Quiero saber más →
        </button>
      </div>
    </div>);

}

function ScrollProgressBar() {
  const [progress, setProgress] = useState(0);

  useEffect(() => {
    const handleScroll = () => {
      const scrollTop = window.scrollY;
      const docHeight = document.documentElement.scrollHeight - window.innerHeight;
      const pct = docHeight > 0 ? scrollTop / docHeight * 100 : 0;
      setProgress(pct);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  return <div className="progress-bar" style={{ width: `${progress}%` }} />;
}

function NewsletterForm() {
  const [email, setEmail] = useState('');
  const [nombre, setNombre] = useState('');
  const [done, setDone] = useState(false);

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    if (email) setDone(true);
  };

  if (done) {
    return (
      <p style={{ fontSize: '18px', color: '#bd8762', fontWeight: 600, fontFamily: "'Dosis', 'Sen', sans-serif" }}>
        ¡Gracias! Te hemos suscrito correctamente.
      </p>);

  }

  return (
    <form onSubmit={handleSubmit} style={{ display: 'flex', gap: '8px', flexWrap: 'wrap', justifyContent: 'center', maxWidth: '600px', margin: '0 auto' }}>
      <input
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email"
        required
        style={{
          flex: '1 1 200px',
          padding: '10px 16px',
          border: '1px solid #212529',
          borderRadius: '5px',
          fontFamily: "'Dosis', 'Sen', sans-serif",
          fontSize: '16px',
          outline: 'none'
        }} />
      
      <input
        type="text"
        value={nombre}
        onChange={(e) => setNombre(e.target.value)}
        placeholder="Nombre"
        style={{
          flex: '1 1 160px',
          padding: '10px 16px',
          border: '1px solid #212529',
          borderRadius: '5px',
          fontFamily: "'Dosis', 'Sen', sans-serif",
          fontSize: '16px',
          outline: 'none'
        }} />
      
      <button type="submit" className="btn-astro" style={{ padding: '10px 24px', fontSize: '16px' }}>
        Suscríbeme
      </button>
    </form>);

}
