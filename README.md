# Sequence-Diagram-for-humanoid-robot
@startuml
actor Human
participant Robot
participant Environment

Human -> Robot: send_command("move up")
Robot -> Environment: check_obstacles()
Environment -> Robot: return obstacle status
Robot -> Robot: move("up")
Robot -> Human: receive_feedback("Moved up successfully.")

Human -> Robot: send_command("pick up object")
Robot -> Environment: get_objects()
Environment -> Robot: return object status
Robot -> Robot: pick_up(object)
Robot -> Human: receive_feedback("Picked up object.")

Human -> Robot: send_command("place object")
Robot -> Robot: place(object)
Robot -> Human: receive_feedback("Placed object successfully.")

Human -> Robot: send_command("charge")
Robot -> Robot: charge()
Robot -> Human: receive_feedback("Charging complete.")
@enduml
