# ATIVIDADEDEESCOPO
ATIVIDADE ESCOPO
# ==========================================================
# 1. ESCOPO GLOBAL
# Variável declarada fora de qualquer função.
# Acessível em qualquer lugar do programa.
# ==========================================================
variavel_global = "Sou GLOBAL: visível em todo o código!"

def demonstrar_escopo():
    # ==========================================================
    # 2. ESCOPO LOCAL (dentro da função)
    # Variável declarada dentro da função.
    # Só existe e é acessível DENTRO desta função.
    # ==========================================================
    variavel_local = "Sou LOCAL: só existo DENTRO desta função."
    
    print("--- DENTRO DA FUNÇÃO ---")
    
    # É possível acessar a variável GLOBAL DENTRO da função
    print(f"1. Acessando Global (OK): {variavel_global}")
    
    # É possível acessar a variável LOCAL DENTRO da função
    print(f"2. Acessando Local (OK): {variavel_local}")
    
    # Modificando a variável GLOBAL (em Python, é necessário o 'global' para reatribuir)
    global variavel_global
    variavel_global = "GLOBAL foi modificada DENTRO da função!"
    print(f"3. Global após modificação: {variavel_global}")

# Chamando a função para executar o código em seu escopo local
demonstrar_escopo()

print("\n--- FORA DA FUNÇÃO (Escopo Principal) ---")

# ==========================================================
# 3. FORA DA FUNÇÃO (Acessando no Escopo Principal)
# ==========================================================

# A variável GLOBAL é acessível aqui, e você verá a mudança feita na função
print(f"4. Acessando Global (OK): {variavel_global}")

# TENTATIVA DE ACESSAR A VARIÁVEL LOCAL:
# Isso resultará em um erro, pois a 'variavel_local' não existe fora da função.
try:
    print(f"5. Acessando Local (Erro Esperado): {variavel_local}")
except NameError as e:
    print(f"5. Acessando Local (ERRO): {e}")
    print("   -> A variável local foi destruída após a função terminar.")
