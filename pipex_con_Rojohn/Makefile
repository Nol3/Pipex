# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: alcarden <alcarden@student.42malaga.com    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/10/17 13:24:53 by alcarden          #+#    #+#              #
#    Updated: 2023/10/17 13:24:55 by alcarden         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

PROG	= pipex

SRCS 	= srcs/pipex.c srcs/utils.c
OBJS 	= ${SRCS:.c=.o}
MAIN	= srcs/pipex.c

HEADER	= -Iincludes

CC 		= gcc
CFLAGS 	= -Wall -Wextra -Werror -g

.c.o:		%.o : %.c
					@gcc ${CFLAGS} ${HEADER} -c $< -o $(<:.c=.o)

all: 		${PROG}

${PROG}:	${OBJS}
					@echo "\033[33m----Compiling lib----"
					@make re -C ./libft
					@$(CC) ${OBJS} -Llibft -lft -o ${PROG}
					@echo "\033[32mPipex Compiled! ᕦ(\033[31m♥\033[32m_\033[31m♥\033[32m)ᕤ\n"


clean:
					@make clean -C ./libft
					@rm -f ${OBJS} ${OBJS_B}

fclean: 	clean
					@make fclean -C ./libft
					@rm -f $(NAME)
					@rm -f ${PROG}
					@echo "\n\033[31mDeleting EVERYTHING! ⌐(ಠ۾ಠ)¬\n"

re:			fclean all

.PHONY: all clean fclean re