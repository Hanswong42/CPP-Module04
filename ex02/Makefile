NAME		= Abstract

SRC_DIR		= ./
OBJ_DIR		= obj
INC_DIR		= inc

SRC_FILES	= main.cpp Animal.cpp Dog.cpp Cat.cpp Brain.cpp

GCC 		= c++
CFLAGS		= -Wall -Wextra -Werror -Wshadow 
C++FLAGS	= -std=c++98
SANITIZE	= -fsanitize=address -g3
RM			= rm -f

OBJ_FILES	= $(addprefix , $(SRC_FILES:.c=.o))

all:		$(NAME)

%.o:		$(SRC_DIR)/%.c
	@mkdir -p obj
	$(GCC) $(C++FLAGS) $(CFLAGS) -I $(INC_DIR) -c $< -o $@

$(LIBFT):
	make -C $(LIBFT_DIR)

$(MLX):
	make -C $(MLX_DIR)

${NAME}:	${LIBFT} $(MLX) ${OBJ_FILES} ${OBJ_BANNER}
	${GCC} -o ${NAME} ${OBJ_FILES} $(SANITIZE)

test: $(NAME)
	@./$(NAME) > output.log

clean:
	$(RM) $(OBJ_DIR)/*

fclean:
	$(RM) $(NAME)
	$(RM) $(OBJ_DIR)/*

re:			fclean all

.PHONY:		all clean fclean re
