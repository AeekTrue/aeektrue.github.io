# DearPyGUI
```python
import dearpygui.dearpygui as dpg
import threading
import time

def update_progress_bar():
    for i in range(101):  # Progress from 0 to 100
        dpg.set_value("progress_bar", i / 100.0)  # Update the progress bar
        time.sleep(0.05)  # Simulate work being done (50ms per step)

def start_progress_thread():
    thread = threading.Thread(target=update_progress_bar, daemon=True)
    thread.start()

def create_plot_window():
    with dpg.window(label="Plot Example", pos=(400, 0)):
        x_data = [0.1 * i for i in range(100)]
        y_data = [x ** 2 for x in x_data]  # Example: y = x^2
        with dpg.plot(label="Example Plot", width=400, height=300):
            dpg.add_plot_axis(dpg.mvXAxis, label="X-Axis")
            y_axis = dpg.add_plot_axis(dpg.mvYAxis, label="Y-Axis")
            dpg.add_line_series(x_data, y_data, label="y = x^2", parent=y_axis)

def load_custom_font():
    with dpg.font_registry():
        font = dpg.add_font("./data/font.ttf", 20)
        dpg.bind_font(font)

dpg.create_context()

# Configure the application to enable docking
dpg.configure_app(docking=True, docking_space=True)

# Load the custom font
load_custom_font()

dpg.create_viewport(title='Progress Bar and Plot Example', width=800, height=600)

with dpg.window(label="Main Window"):
    dpg.add_button(label="Start Progress", callback=start_progress_thread)
    dpg.add_progress_bar(tag="progress_bar", default_value=0.0, width=300)

# Create the plot window
create_plot_window()

dpg.setup_dearpygui()
dpg.show_viewport()
dpg.start_dearpygui()
dpg.destroy_context()
```
