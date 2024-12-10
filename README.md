# Habilitar el uso del mouse
set -g mouse on

# Incrementar el límite de historial
set -g history-limit 5000

# Usar prefix Shift + A (Shift actúa como modificador primario)
set-option -g prefix S-a
unbind C-b
bind S-a send-prefix

# Atajos usando Shift

# Shift + T: Crear una nueva ventana
bind T new-window

# Shift + W: Cerrar ventana
bind W kill-window

# Navegación entre paneles con Shift + flechas
bind -n S-Right select-pane -R
bind -n S-Left select-pane -L
bind -n S-Up select-pane -U
bind -n S-Down select-pane -D

# Recargar configuración con Shift + R
bind R source-file ~/.tmux.conf \; display-message "Configuración recargada"

# Dividir paneles
bind S-\ split-window -h  # Dividir horizontalmente
bind S-| split-window -v  # Dividir verticalmente

# Estilo de barra de estado
set-option -g status-bg black
set-option -g status-fg white
set-option -g status-left-length 50
set-option -g status-right-length 50
set-option -g status-interval 5

set-option -g status-left '#[fg=green](#S) '
set-option -g status-right '#[fg=cyan]#(whoami)@#H #[fg=white]%H:%M %d-%b-%y'
