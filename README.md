# jogodavelha
def desenhar_tabuleiro(tabuleiro):

    print(tabuleiro[0] + ' | ' + tabuleiro[1] + ' | ' + tabuleiro[2])
    print('--+---+--')
    print(tabuleiro[3] + ' | ' + tabuleiro[4] + ' | ' + tabuleiro[5])
    print('--+---+--')
    print(tabuleiro[6] + ' | ' + tabuleiro[7] + ' | ' + tabuleiro[8])

def verificar_vitoria(tabuleiro, jogador):
    if tabuleiro[0] == jogador and tabuleiro[1] == jogador and tabuleiro[2] == jogador:
        return True
    if tabuleiro[3] == jogador and tabuleiro[4] == jogador and tabuleiro[5] == jogador:
        return True
    if tabuleiro[6] == jogador and tabuleiro[7] == jogador and tabuleiro[8] == jogador:
        return True

    if tabuleiro[0] == jogador and tabuleiro[3] == jogador and tabuleiro[6] == jogador:
        return True
    if tabuleiro[1] == jogador and tabuleiro[4] == jogador and tabuleiro[7] == jogador:
        return True
    if tabuleiro[2] == jogador and tabuleiro[5] == jogador and tabuleiro[8] == jogador:
        return True

    if tabuleiro[0] == jogador and tabuleiro[4] == jogador and tabuleiro[8] == jogador:
        return True
    if tabuleiro[2] == jogador and tabuleiro[4] == jogador and tabuleiro[6] == jogador:
        return True
    return False

def jogo_da_velha():
    tabuleiro = [' '] * 9
    jogador_atual = 'X'

    while True:
        desenhar_tabuleiro(tabuleiro)
        print("É a vez do jogador " + jogador_atual)
        jogando = int(input("Digite um valor de 0 a 8 para fazer sua jogada: "))

        if tabuleiro[jogando] == ' ':
            tabuleiro[jogando] = jogador_atual

            if verificar_vitoria(tabuleiro, jogador_atual):
                desenhar_tabuleiro(tabuleiro)
                print("O jogador " + jogador_atual + " venceu!")
                break

            if jogador_atual == 'X':
                jogador_atual = 'O'
            else:
                jogador_atual = 'X'
        else:
            print("Posição já preenchida. Tente novamente.")

jogo_da_velha()
