# todolist.py

class ToDoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)
        print(f"Task '{task}' added to the to-do list.")

    def view_tasks(self):
        if not self.tasks:
            print("No tasks in the to-do list.")
        else:
            print("To-Do List:")
            for index, task in enumerate(self.tasks, start=1):
                print(f"{index}. {task}")

    def delete_task(self, task_index):
        try:
            task_index = int(task_index)
            if 1 <= task_index <= len(self.tasks):
                deleted_task = self.tasks.pop(task_index - 1)
                print(f"Task '{deleted_task}' deleted from the to-do list.")
            else:
                print("Invalid task index.")
        except ValueError:
            print("Invalid task index.")

if __name__ == "__main__":
    todo_list = ToDoList()

    while True:
        print("\nOptions:")
        print("1. Add Task")
        print("2. View Tasks")
        print("3. Delete Task")
        print("4. Exit")

        choice = input("Enter your choice (1/2/3/4): ")

        if choice == '1':
            task = input("Enter the task: ")
            todo_list.add_task(task)

        elif choice == '2':
            todo_list.view_tasks()

        elif choice == '3':
            task_index = input("Enter the task index to delete: ")
            todo_list.delete_task(task_index)

        elif choice == '4':
            print("Exiting the to-do list. Goodbye!")
            break

        else:
            print("Invalid choice. Please choose a valid option.")
