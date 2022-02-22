# katas
# %% [markdown]
# # Manual de la Nave

# %%
import ipywidgets as widgets

ignition = widgets.ToggleButton(
    value=False,
    description='Iniciar Launch',
    button_style='success',
    tooltip='Engage your Launch',
    icon='rocket'
)

output = widgets.Output()

display(ignition, output)

def on_value_change(change):
    with output:
        if change['new'] == True:
            print("Nave Iniciada!")
        else:   
            print("Nave Detenida")

ignition.observe(on_value_change, names='value')

# %% [markdown]
# ## Velocidad de la nave
# 
# Muestra los segundos necesarios para pasar de 0 a 11200 metros por segundo, dada la aceleración de la nave en metros por segundo.

# %%
endVelocity = 11200
startVelocity = 0
acceleration = 9.8

time = (endVelocity - startVelocity) / acceleration
print("Tiempo para alcanzar la velocidad deseada = ", time)
