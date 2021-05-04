# Table/Model

We had created_at and updated_at columns for all the models. To keep things DRY, any column referenced more than once. 

## Schema

(🌱: primary key; <ins>underlined</ins>: foreign key)

- <strong>User</strong>
  - user_id: integer 🌱
  - username: string
  - email: string
  - encrypted_password: string
  - confirmation_token: string
  - remember_token: string
  - admin: boolean
- <strong>UserPlant</strong>
  - plant_id: integer 🌱
  - <ins>user_id: integer</ins>
  - name: string
  - age: float
  - plant_type: string
  - image_url: string
  - description: string
- <strong>Reminder</strong>
  - reminder_id: integer 🌱
  - <ins>user_plant_id: integer</ins>
  - <ins>user_id: integer</ins>
  - tick_time: time
  - description: string
  - reminder_type: enum
- <strong>ChatbotMessage</strong>
  - chatbot_message_id: integer 🌱
  - <ins>user_id: integer</ins>
  - time_sent: datetime
  - from_bot: boolean
  - content: string
- <strong>Post</strong>
  - post_id: integer 🌱
  - <ins>user_id: integer</ins>
  - topic: enum
  - title: string
  - body: string
- <strong>Reply</strong>
  - reply_id: integer 🌱
  - <ins>user_id: integer</ins>
  - <ins>post_id: integer</ins>
  - body: string
- <strong>PlantType</strong>
  - plant_type_id: integer 🌱
  - name: string

  [Next page](database_diagram.md)