#JOÃO FABRICIO RADMANN DOS SANTOS
#IMPLEMENTAÇÃO COMPUTACIONAL DO MÉTODO DE JACOBI
#LINGUAGEM DE PROGRAMAÇÃO: PYTHON
def jacobi (A,b,vetorSolucao,iteracoes):
  iteracao = 0
  vetorAux = []
  for k in range(len(vetorSolucao)):
    vetorAux.append(0)

  while iteracao < iteracoes:
    for i in range(len(A)):
      x = b[i]
      for j in range(len(A)):
        if i != j:
          x -= A[i][j]*vetorSolucao[j]
      x /= A[i][i]
      vetorAux[i] = x
    print('X da etapa: ',iteracao, ' Aproximação: ',vetorSolucao)
    iteracao += 1

    for p in range(len(vetorAux)):
      vetorSolucao[p] = vetorAux[p]

  print('X da etapa: ',iteracao, ' Aproximação: ',vetorSolucao)


jacobi([[2,1],[3,4]],[1,-1],[0,0],3)
#solucao desse sistema: (1,-1)
#a partir da iteracao 78, obtem-se o resultado exato


jacobi([[10,2,1],[1,5,1],[2,3,10]],[7,-8,6],[0,0,0],38)
#solução desse sistema: (1,-2,1)
#a partir da iteracao 38, obtem-se o resultado exato


#jacobi([[4,-1,-1,0,0],[-1,4,-1,-1,0],[-1,-1,4,-1,-1],[0,-1,-1,4,-1],[0,0,-1,-1,4]],[-1,2,6,2,-1],[0,0,0,0,0],200)
#a solução exata desse sistema é: (1,2,3,2,1)
#a partir da iteração 119, obtem-se o resultado exato
