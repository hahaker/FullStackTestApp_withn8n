
простейшая конструкция обработки пост запросов
<img width="1082" height="423" alt="image" src="https://github.com/user-attachments/assets/e5906793-dd8d-4df1-8c51-b9487fcc4312" />


получение данных от пользователя с формы
<img width="474" height="701" alt="image" src="https://github.com/user-attachments/assets/fbde83ff-bfa5-485c-8145-b2fbc6bf2cf8" />

для дальнейшей интеграции с EspoCRM 
изменения в n8n
 HTTP Request узел:
URL: https://your-espocrm.com/api/v1/Lead

Authentication: Basic Auth
  Username: n8n-integration
  Password: SuperSecret123!

Body (JSON):
{
  "firstName": "{{ $node["Function"].json.firstName }}",
  "lastName": "{{ $node["Function"].json.lastName || '' }}",
  "emailAddress": "{{ $node["Function"].json.emailAddress }}",
  "phoneNumber": "{{ $node["Function"].json.phoneNumber }}",
  "description": "{{ $node["Function"].json.description }}",
  "source": "Website",
  "status": "New"
}
