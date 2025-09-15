# lab5_navigation.py
# Simulating Information Architecture & Navigation (single program)

print("Welcome to Human Computer Interaction!")
print("Exploring Information Architecture with Python...\n")

website_name = "HCI Demo Site"
author = "Student Name"
print("Website:", website_name)
print("Author:", author)

sections = {
    "Home" : "Welcome to the Home Page. This is where users first arrive.",
    "About" : "About page: mission, team, and background information.",
    "Services" : "Services page: see the list of services we provide.",
    "Contact" : "Contact page: email and phone details."
}

services = ["Web Design", "App Development", "Data Analysis"]

def show_menu():
    print("=== Navigation Menu ===")
    for key in sections.keys():
        print("-", key)
    print("- Exit (Type 'Exit' to quit)\n")

while True:
    show_menu()
    choice = input("Where do you want to go? (Type page name or 'Exit'):").strip

    if choice.lower() == 'exit':
        print("\nThank you for exploring the system. Goodbye!")
        break
        
    matched = None
    for page in sections:
        if choice.lower() == page.lower():
            matched = page
            break

    if matched:
        print(f"\nYou are now on the {matched} page.")
        print("Content:" , sections[matched])

        if matched == "Services":
            print("\nOur Services:")
            for s in services:
                print("-", s)

        go_back = input("\nDo you want to open another page? (y/n): ").strip().lower()
        if go_back == "n":
            print("\nEnding session. Goodbye!")
            break
        else:
            print("")

else: 
    print("\nPage not found. Please choose a valid page from the menu.\n")
