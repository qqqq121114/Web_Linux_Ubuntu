<template>
  <nav class="cyber-nav">
    <router-link to="/" class="nav-brand">CyberGame</router-link>
    <div class="nav-links">
      <router-link to="/register" class="cyber-button">Register</router-link>
      <router-link to="/login" class="cyber-button">Login</router-link>
    </div>
  </nav>
</template>

<style scoped>
.cyber-nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 30px;
  background: rgba(0, 0, 0, 0.7);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--cyber-text);
  box-shadow: 0 0 20px rgba(255, 184, 0, 0.15);
  z-index: 1000;
}

.nav-brand {
  font-size: 1.8em;
  color: var(--cyber-text);
  text-decoration: none;
  font-family: 'Share Tech Mono', monospace;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  text-shadow: 0 0 10px var(--cyber-glow);
  transition: all 0.3s ease;
}

.nav-brand:hover {
  text-shadow: 0 0 20px var(--cyber-glow);
  transform: scale(1.05);
}

.nav-links {
  display: flex;
  gap: 20px;
}

.cyber-button {
  padding: 8px 20px;
  background: rgba(255, 184, 0, 0.1);
  border: 1px solid var(--cyber-text);
  color: var(--cyber-text);
  text-decoration: none;
  font-family: 'Share Tech Mono', monospace;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  font-size: 0.9em;
  transition: all 0.3s ease;
  border-radius: 4px;
  backdrop-filter: blur(5px);
  position: relative;
  overflow: hidden;
}

.cyber-button::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(
    45deg,
    transparent,
    rgba(255, 184, 0, 0.1),
    transparent
  );
  transform: rotate(45deg);
  transition: all 0.3s ease;
  opacity: 0;
}

.cyber-button:hover {
  background: rgba(255, 184, 0, 0.2);
  box-shadow: 0 0 20px rgba(255, 184, 0, 0.3);
  transform: translateY(-2px);
}

.cyber-button:hover::before {
  animation: shine 1s;
  opacity: 1;
}

@keyframes shine {
  0% {
    transform: translateX(-100%) rotate(45deg);
  }
  100% {
    transform: translateX(100%) rotate(45deg);
  }
}

/* 响应式设计 */
@media (max-width: 768px) {
  .cyber-nav {
    padding: 0 15px;
  }

  .nav-brand {
    font-size: 1.4em;
  }

  .cyber-button {
    padding: 6px 15px;
    font-size: 0.8em;
  }
}
</style> 