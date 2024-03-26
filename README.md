import matplotlib.pyplot as plt
from matplotlib.patches import FancyBboxPatch

# Define the positions and labels for the nodes
nodes = {
    "Introduction": (0, 2),
    "Enhancing Group Traveller Experiences": (-2, 1),
    "Selecting the Right Corporate Accommodation Partner": (0, 1),
    "Navigating Sustainable Corporate Travel": (2, 1),
    "Global Sustainability Regulatory Trends": (-2, 0),
    "Action Plan for Evaluating Accommodation Partners": (0, 0),
    "Conclusion": (2, 0),
}

# Define the connections between nodes
connections = [
    ("Introduction", "Enhancing Group Traveller Experiences"),
    ("Introduction", "Selecting the Right Corporate Accommodation Partner"),
    ("Introduction", "Navigating Sustainable Corporate Travel"),
    ("Enhancing Group Traveller Experiences", "Global Sustainability Regulatory Trends"),
    ("Enhancing Group Traveller Experiences", "Action Plan for Evaluating Accommodation Partners"),
    ("Selecting the Right Corporate Accommodation Partner", "Action Plan for Evaluating Accommodation Partners"),
    ("Navigating Sustainable Corporate Travel", "Global Sustainability Regulatory Trends"),
    ("Navigating Sustainable Corporate Travel", "Action Plan for Evaluating Accommodation Partners"),
    ("Global Sustainability Regulatory Trends", "Conclusion"),
    ("Action Plan for Evaluating Accommodation Partners", "Conclusion"),
]

# Function to draw the arrows between nodes
def draw_arrows(ax, start, end):
    ax.annotate("", xy=end, xytext=start, arrowprops=dict(arrowstyle="->"))

# Create the figure and axis
fig, ax = plt.subplots(figsize=(10, 6))

# Draw nodes
for label, pos in nodes.items():
    ax.text(pos[0], pos[1], label, ha='center', va='center', fontsize=12, bbox=dict(facecolor='lightblue', edgecolor='black', boxstyle='round,pad=0.3'))

# Draw connections
for connection in connections:
    draw_arrows(ax, nodes[connection[0]], nodes[connection[1]])

# Remove axes and set title
ax.axis('off')
ax.set_title('Comprehensive Report on Corporate Travel Business', fontsize=16)

# Show plot
plt.show()
