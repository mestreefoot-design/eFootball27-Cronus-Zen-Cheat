# Guia de Configuração - CoreX FC27

## 🎯 Configurações Recomendadas

### Para Defesa Agressiva (Van Dijk Style)
```gpc
define TACKLE_POWER = 120;      // Aumenta força do desarme
define SPRINT_BOOST = 80;       // Reduz para melhor posicionamento
define DRIBBLE_SPEED = 60;      // Menos drible, mais defesa
```

### Para Ataque Rápido (Neymar Style)
```gpc
define SPRINT_BOOST = 150;      // Máximo de velocidade
define DRIBBLE_SPEED = 120;     // Dribbles mais rápidos
define SHOOT_POWER = 100;       // Chutes mais potentes
```

### Para Jogo Equilibrado
```gpc
define SPRINT_BOOST = 100;      // Padrão
define TACKLE_POWER = 100;      // Padrão
define SHOOT_POWER = 85;        // Padrão
define DRIBBLE_SPEED = 90;      // Padrão
```

## 🔄 Timings Dinâmicos

O script detecta automaticamente a posição do jogador:

- **Defesa (LT > 50)**: Ativa modo defensivo
- **Ataque (RT > 50)**: Ativa modo ofensivo
- **Meio (Neutro)**: Modo equilibrado

## 📊 Monitoramento de Stamina

O sistema gerencia automaticamente a resistência:

```gpc
if(stamina_level < 30) {
    set_val(XB1_RT, 0);  // Para o sprint
    wait(100);            // Aguarda recuperação
}
```

## 🎮 Customização de Combos

Você pode criar seus próprios combos editando as funções:

```gpc
function meu_combo() {
    set_val(XB1_RB, 100);  // Skill move
    wait(30);
    set_val(XB1_B, 100);   // Chute
    wait(60);
    set_val(XB1_B, 0);
}
```

## 🚀 Performance Tips

1. **Reduzir Lag**: Diminua `REACTION_BOOST` para 50ms
2. **Melhorar Precisão**: Aumente `SHOOT_POWER` para 100
3. **Dribbles Mais Fluidos**: Aumente `DRIBBLE_SPEED` para 110
4. **Defesa Mais Forte**: Aumente `TACKLE_POWER` para 120

## 🔐 Segurança

- O script não modifica dados do jogo
- Apenas simula inputs do controller
- Compatível com anti-cheat (não detectável)
- Use responsavelmente

---

**Última atualização**: 16/08/2026
