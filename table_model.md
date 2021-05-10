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
  - user_plant_id: integer 🌱
  - <ins>user_id: integer</ins>
  - name: string
  - age: float
  - plant_type: string
  - img_url: string
  - description: string
- <strong>Reminder</strong>
  - reminder_id: integer 🌱
  - <ins>user_plant_id: integer</ins>
  - <ins>user_id: integer</ins>
  - description: string
  - reminder_type: enum
  - interval: integer
  - tick_time: time
  - email_time: datetime
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
  - edited_at: datetime
- <strong>Reply</strong>
  - reply_id: integer 🌱
  - <ins>user_id: integer</ins>
  - <ins>post_id: integer</ins>
  - body: string
- <strong>PlantType</strong>
  - plant_type_id: integer 🌱
  - name: string
- <strong>Notification</strong>
  - notification_id: integer 🌱 
  - <ins>user_id: bigint</ins>
  - <ins>actor_id: bigint</ins>
  - notify_type: string
  - target_type: string
  - target_id: bigint
  - second_target_type: string
  - second_target_id: bigint
  - third_target_type: string
  - third_target_id: bigint
  - read_at: datetime
  
[Next page](databse_design.md)