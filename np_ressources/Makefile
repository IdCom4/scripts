# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
+#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#+#    #+#              #
###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME =
SRCS =
OBJECTS = $(SRCS:.c=.o)
LIBFT_PATH = ./libft
LIBFT_A = $(LIBFT_PATH)/libft.a
CC = gcc
CFLAGS = -Wall -Wextra -Werror
PRCS_CLR = \033[1;33m
SCSS_CLR = \033[0;32m
MKFLE_CLR = \033[0;33m
MKFLE = $(MKFLE_CLR)

all : $(NAME)


$(NAME): $(LIBFT_A) $(OBJECTS)
	@printf '$(MKFLE)${PRCS_CLR}%-65s' ">> Compiling executable..."
	@$(CC) $(CFLAGS) -o $(NAME) objs/$(OBJECTS) $(LIBFT_A)
	@printf '\r$(MKFLE)${SCSS_CLR}%-65s\n' ">> $(NAME) created."

$(LIBFT_A):
	@make -C $(LIBFT_PATH)

%.o: %.c
	@if [[ ! -d "objs" ]]; then \
		mkdir objs ; \
	fi
	@printf '$(MKFLE)${PRCS_CLR}%-60s' ">> Compiling $<..."
	@$(CC) $(CFLAGS) -o objs/$@ -c $<
	@printf "${SCSS_CLR}[OK]\r"

clean:
	@make clean -C $(LIBFT_PATH)
	@printf "$(MKFLE)${PRCS_CLR}>> Deleting objects...\r"
	@rm -rf objs
	@echo "$(MKFLE)${SCSS_CLR}>> Objects deleted.       "

fclean: clean
	@printf "$(MKFLE)${PRCS_CLR}>> Deleting libft.a...\r"
	@rm -f $(LIBFT_A)
	@echo "$(MKFLE)${SCSS_CLR}>> libft.a deleted.       "
	@printf "$(MKFLE)${PRCS_CLR}>> Deleting $(NAME)...\r"
	@rm -f $(NAME)
	@echo "$(MKFLE)${SCSS_CLR}>> $(NAME) deleted.       "

re: fclean all
	@echo "$(MKFLE)${SCSS_CLR}>> RE successfully done."

.PHONY: all clean fclean re
