@startuml
left to right direction
skinparam packageStyle rectangle
skinparam usecase {
    BackgroundColor LightCyan
    BorderColor DarkCyan
}
skinparam actor {
    BackgroundColor Azure
    BorderColor DarkCyan
}

actor "Cliente (Hóspede)" as Cliente
actor "Administrador do Hotel" as Admin

rectangle "Sistema Bookify" {
    
    ' Casos de Uso do Cliente
    usecase "Realizar Cadastro" as UC1
    usecase "Fazer Login" as UC2
    usecase "Responder Quiz/Questionário" as UC3
    usecase "Consultar Quartos Disponíveis" as UC4
    usecase "Realizar Reserva" as UC5
    usecase "Contatar Hotel (WhatsApp)" as UC6
    usecase "Fornecer Feedback Pós-estadia" as UC7
    
    ' Casos de Uso do Administrador
    usecase "Gerenciar Perfis" as UC8
    usecase "Gerenciar Quartos e Disponibilidade" as UC9
    usecase "Gerenciar Relatórios" as UC10
    usecase "Gerenciar Rankeamento de Clientes" as UC11
    usecase "Gerenciar Parceiros" as UC12
    usecase "Realizar Check-in e Check-out" as UC13
    usecase "Atualizar Status (Limpeza e Ocupação)" as UC14
}

' Relações do Cliente
Cliente --> UC1
Cliente --> UC2
Cliente --> UC3
Cliente --> UC4
Cliente --> UC5
Cliente --> UC6
Cliente --> UC7

' Regras explícitas do texto (Includes)
UC4 ..> UC2 : <<include>>
UC4 ..> UC3 : <<include>>

' Relações do Administrador
Admin --> UC8
Admin --> UC9
Admin --> UC10
Admin --> UC11
Admin --> UC12
Admin --> UC13
Admin --> UC14

@enduml
