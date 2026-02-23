 Simple To-Do List Application

tasks = []

def show_tasks():
    if len(tasks) == 0:
        print("\nNo tasks in your list.")
    else:
        print("\nYour To-Do List:")
        for i in range(len(tasks)):
            print(f"{i + 1}. {tasks[i]}")

while True:
    print("\n--- TO-DO LIST MENU ---")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Mark Task as Completed")
    print("4. Delete Task")
    print("5. Exit")

    choice = input("Enter your choice (1-5): ")

    if choice == "1":
        task = input("Enter new task: ")
        tasks.append(task)
        print("Task added successfully!")

    elif choice == "2":
        show_tasks()

    elif choice == "3":
        show_tasks()
        num = int(input("Enter task number to mark as completed: "))
        if 1 <= num <= len(tasks):
            tasks[num - 1] = tasks[num - 1] + " ✔"
            print("Task marked as completed!")
        else:
            print("Invalid task number.")

    elif choice == "4":
        show_tasks()
        num = int(input("Enter task number to delete: "))
        if 1 <= num <= len(tasks):
            removed = tasks.pop(num - 1)
            print(f"Task '{removed}' deleted.")
        else:
            print("Invalid task number.")

    elif choice == "5":
        print("Exiting program. Goodbye!")
        break

    else:
        print("Invalid choice. Please select 1-5.")
