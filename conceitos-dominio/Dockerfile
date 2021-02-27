.data
	espace: .asciiz "\n"
.text
main:	
	li $v0, 5 			# executa o scanf da aplicação
	syscall
	move $t0, $v0			# move o valor para o registrador $t0
	
	addi $s2, $zero, 0 		# Atribui o valor de $s2 a zero que é o resultado
	addi $s1, $zero, 0 		# Atribui o valor de $s1 a zero que é o i

FOR:	slt $t2, $s1, $t0 		# verificar se i < n 
	beq $t2, $zero, FINISH 		# se o valor de i !< 0, sai do laço e retorna para o FINISH
	
	li $v0, 5			# executa o scanf da aplicação
	syscall
	move $t1, $v0
	
	add $s2, $s2, $t1		#resultado += valor
	addi $s1, $s1, 1 		#i++
	j FOR
	
FINISH:	li $v0, 1
	move $a0, $s2
	syscall
	
	li $v0, 4
	la $a0, espace
	syscall
	
	li $v0, 10
	syscall
