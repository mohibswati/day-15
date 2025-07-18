waste_ideas = {
    "plastic": ["Make planters", "DIY bricks", "Bottle lamps"],
    "paper": ["Make gift bags", "Use in compost", "Create paper mash art"],
    "food": ["Compost", "Biofuel", "Animal feed"],
    "glass": ["Make decor items", "Reuse jars", "Mosaic art"]
}
def show_menu():
    print("1. View Reuse Ideas")
    print("2. Save an Idea")
    print("3. Search by Waste Type")
    print("4. Exit")
def save_idea(waste, idea):
    with open("reuse_ideas.txt", "a") as f:
        f.write(f"{waste}: {idea}\n")
    print("Idea saved!")
while True:
    show_menu()
    choice = input("Choose an option (1-4): ")
    if choice == "1":
        for waste, ideas in waste_ideas.items():
            print(f"\n{waste.title()} Ideas:")
            for i in ideas:
                print(f"- {i}")
    elif choice == "2":
        w = input("Enter waste type: ").lower()
        i = input("Enter your reuse idea: ")
        save_idea(w, i)
    elif choice == "3":
        w = input("Enter waste type to search: ").lower()
        found = waste_ideas.get(w)
        if found:
            print(f"\nIdeas for {w.title()}:")
            for i in found:
                print(f"- {i}")
        else:
            print("No ideas found for this type.")
    elif choice == "4":
        print("Goodbye!")
        break
    else:
        print("Invalid choice.")
