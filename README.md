# MonitorDash

# Building an Interactive Monitoring Dashboard with Streamlit

This guide will walk you through creating an interactive web application using Streamlit. The app will monitor various parameters and Key Performance Indicators (KPIs) of Large Language Models (LLMs) and network services, displaying the results in a radar (spider) chart. Users can select different time frames—such as current, daily average, weekly average, and monthly average—to view the data.

## Prerequisites

Before you begin, ensure you have the following installed on your computer:

- **Python**: Version 3.7 or later. You can download it from the [official website](https://www.python.org/downloads/).

- **pip**: Python's package installer, which typically comes bundled with Python. You can verify its installation by running `pip --version` in your command prompt or terminal.

## Step 1: Set Up Your Project Environment

1. **Create a Project Folder**: Organize your work by creating a new folder for your project. You can name it `streamlit_dashboard`.

   ```bash
   mkdir streamlit_dashboard
   cd streamlit_dashboard
   
pip install streamlit plotly pandas

touch app.py

in app.py

put the following code

```python
import streamlit as st
import pandas as pd
import plotly.express as px

# Sample data
data = {
    'Parameter': ['Accuracy', 'Latency', 'Throughput', 'Availability', 'Error Rate'],
    'Current': [0.95, 0.2, 100, 0.99, 0.01],
    'Daily Average': [0.94, 0.25, 95, 0.98, 0.02],
    'Weekly Average': [0.93, 0.3, 90, 0.97, 0.03],
    'Monthly Average': [0.92, 0.35, 85, 0.96, 0.04]
}
df = pd.DataFrame(data)

# Streamlit app
st.title('Monitoring Dashboard')

# Time frame selection
time_frame = st.selectbox(
    'Select Time Frame',
    ('Current', 'Daily Average', 'Weekly Average', 'Monthly Average')
)

# Radar chart
fig = px.line_polar(
    df,
    r=df[time_frame],
    theta='Parameter',
    line_close=True,
    title=f'Parameter Results - {time_frame}'
)
fig.update_traces(fill='toself')
st.plotly_chart(fig)
```
Explanation of the Code:

__Import Statements:__ Import the necessary libraries.

__Sample Data:__ Define a dictionary containing parameters and their corresponding values for different time frames. This data is then converted into a DataFrame using Pandas.

__Streamlit App Title:__ Set the title of the web application.

__Time Frame Selection:__ Create a dropdown menu (selectbox) that allows users to select the desired time frame.

__Radar Chart:__ Generate a radar chart using Plotly based on the selected time frame and display it in the app.




_Run the App:_

  ```bash
cd path/to/streamlit_dashboard
streamlit run app.py

```css
::contentReference[oaicite:0]{index=0}
 

