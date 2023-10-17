# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: alcarden <alcarden@student.42malaga.com    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/10/17 13:24:53 by alcarden          #+#    #+#              #
#    Updated: 2023/10/17 18:56:00 by alcarden         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

PROG	= pipex
SRC 	= src/pipex.c src/utils.c
OBJS 	= ${SRC:.c=.o}
MAIN	= src/pipex.c
LIBFT 	= libft/libft.a
CFLAGS 	= -Wall -Wextra -Werror -g


src/%.o : src/%.c
	gcc $(CFLAGS) -c $< -o $@

$(LIBFT):
	@make -C libft

all: 		${PROG}

${PROG}:	${OBJS}
					@echo " Compiling libft..."
					@make re -C ./libft
					@gcc ${OBJS} $(LIBFT) -o ${PROG}
					@echo "Pipex Compiled!\n"

clean:
					@make clean -C ./libft
					@rm -f ${OBJS} ${OBJS_B}

fclean: 	clean
					@make fclean -C ./libft
					@rm -f $(NAME)
					@rm -f ${PROG}
					@echo "Deleting EVERYTHING!\n"

re:			fclean all

.PHONY: all clean fclean re