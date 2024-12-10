# tmux-examo-mac


# Habilitar el uso del mouse
set -g mouse on

# Incrementar el límite de historial
set -g history-limit 5000

# Usar prefix como Ctrl + a en lugar de Ctrl + b (más ergonómico en teclados Mac)
set-option -g prefix C-a
unbind C-b
bind C-a send-prefix

# Remapear las teclas Option y Command
# Nota: Option (⌥) se usa como Meta en muchas configuraciones. Command no tiene un mapeo directo.
set -g xterm-keys on

# Rebind para facilitar el uso en Mac:
# Command + t para crear nueva ventana
bind t new-window

# Command + w para cerrar ventana
bind w kill-window

# Command + → para moverse al siguiente panel
bind -n M-Right select-pane -R

# Command + ← para moverse al panel anterior
bind -n M-Left select-pane -L

# Command + ↑ para moverse arriba
bind -n M-Up select-pane -U

# Command + ↓ para moverse abajo
bind -n M-Down select-pane -D

# Recargar configuración con Command + r
bind r source-file ~/.tmux.conf \; display-message "Configuración recargada"

# Dividir paneles (más accesible con Option/Meta)
bind | split-window -h
bind - split-window -v

# Estilo de barra de estado
set-option -g status-bg black
set-option -g status-fg white
set-option -g status-left-length 50
set-option -g status-right-length 50
set-option -g status-interval 5

set-option -g status-left '#[fg=green](#S) '
set-option -g status-right '#[fg=cyan]#(whoami)@#H #[fg=white]%H:%M %d-%b-%y'

# Pane border
set-option -g pane-border-fg black
set-option -g pane-active-border-fg green
