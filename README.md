# InternGlobalTech
# Bar

import matplotlib.pyplot as plt

categories = ['A', 'B', 'C','D','E']
values = [25, 30, 50, 30, 25]

plt.bar(categories, values, color= ('red', 'blue', 'orange','pink','yellow'), 
        edgecolor=('yellow', 'pink', 'red', 'orange','blue'))
plt.xlabel('Level')
plt.ylabel('Values')
plt.title('Bar Chart')
plt.show()


# Line

x = [1, 3, 6, 2, 5]
y = [10, 15, 20, 25, 30]

plt.plot(x, y, marker='o', c='r')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('Line Chart')
plt.show()


# Pie

Performance = ['Excellent', 'Good', 'Average','Poor']
sizes = [30, 15, 30, 25]

plt.figure(figsize=(8,8))
plt.pie(sizes, labels=Performance, startangle=0, explode=[0.2,0,0,0],
        shadow=True, colors=('orange','r','b','y'), autopct='%1.1f%%')
plt.legend(title="Performance")
plt.title('Pie Chart')
plt.show()


# semi pie

Performance = ['Excellent', 'Good', 'Average','Poor']
sizes = [30, 40, 30, 20]
plt.figure(figsize=(8,12))

fig, ax = plt.subplots()
ax.pie(sizes, labels=Performance, startangle=0, explode=[0,0.2,0,0], shadow="True", 
       autopct='%1.1f%%', wedgeprops=dict(width=0.4), colors=('orange','r','b','y'))

centre_circle = plt.Circle((0, 0), 0.2, color='white', fc='white', linewidth=1.25)

fig = plt.gcf()
fig.gca().add_artist(centre_circle)
plt.legend(title="Performance")

ax.axis('equal')  

plt.title('Semi-Pie Chart')
plt.show()


# Tree

import squarify

sizes = [50, 20, 40, 35, 25, 30, 25]
Demand = ['Python', 'C', 'Java', 'JavaScript', '#c','C++','Php']
plt.figure(figsize=(8,10))

squarify.plot(sizes=sizes, label=Demand, alpha=0.7, color= ('red', 'blue', 'orange', 'pink', 'yellow','green','black'))
plt.legend(title="Demand in 2023")
plt.axis('off')

plt.title('Tree Map')

plt.show()


#Bullet Graph

import numpy as np

def bullet_graph(data, values, ranges):
    fig, ax = plt.subplots(figsize=(10, 2))

    for i in range(len(data)):
        ax.barh(y=0, width=data[i], height=0.5, left=ranges[i][0], color='orange')

        ax.barh(y=0, width=values[2], height=0.5, left=values[1], color='red')
        
    for i in range(len(ranges)):
        ax.axvline(x=ranges[i][0], color='yellow', linestyle='--', linewidth=2)
        ax.axvline(x=ranges[i][1], color='black', linestyle='--', linewidth=2)

    ax.set_yticks([])
    ax.set_xlabel(values[0])

    plt.title('Bullet Chart')
    plt.show()

data = [60]  
values = ['Level', 80, 45, 120]   
ranges = [(0, 50), (50, 90), (90, 120)]  

bullet_graph(data, values, ranges)
