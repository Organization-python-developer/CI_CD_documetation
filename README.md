## CI / CD nima va uni qanday ishlatish munkin ?
## <center> CI / CD o'zi nima? </center>

<p>txt
Ushbu turkum maqolalardan ko'zlangan asosiy maqsad, web servislarini reliz qilish jarayoni bilan qiynalayotgan, dasturning yangi imkoniyatlarni foydalanuvchilariga ishonchli va tez yetkazishda muammolarga duch kelayotgan jamoalar (team) uchun frontendda qo'llaniladigan keng tarqalgan amaliyotlarni jamlagan muxtasar qo'llanma sifatida yozildi. Maqoladagi ko'rsatmalar asosan kamida 2-4 kishilik jamoa bo'lib ishlayotgan frontend dasturchilar uchun qaratilgan bo'lsada, ba'zi umumiy tushunchalar backend developerlar uchun ham foydali bo'lishi mumkin. Ushbu post juda ko'plab men tanigan va shaxsan tanimagan dasturchilarning tajribalaridan kelib chiqib yozilganiga qaramay albatta xato va kamchiliklardan holi emas. Agar biron xato yoki kamchilik topsangiz albatta sharhlar bandida buni bildiring!
</p>

---
### CI / CD o`zi nima ?

<p>
Dasturiy ta'minotni reliz qilish, agar to'g'ri tashkil etilmasa, bosh-og'riq-beruvchi va ko'p vaqt talab qiladigan jarayon bo'lishi mumkin. Kodni reliz qilishga tayyor bo'lish bilan bog'liq vaqt majburiyatlari ya'ni deadlinelar ( savdo/marketing bo'limlari bosimi ostida) asab torlarini yanada taranglashtiradi. Buni hal qilishni oson yo'li bormi? Albatta bor, CI/CD 🚀
</p>
 
<p>
    CI ya'ni Continuous Integration: dastur kodiga qo'shilgan har bir o'zgarishni (git commit) dastur kodi joylashgan 
    markaziy repositoryga avtomalashtirilgan shaklda davomiy qo'shib borish 
    CD ya'ni Continuous Delivery(Deployment): dastur kodini avtomalashtirilgan shaklda doimiy deploy qilish amaliyoti.
</p>

# Misol:

<p>
birobir proektiz bor u proektiz uchun test yozgansiz masalan: "pytest" moduli orqali --> "python -m pytest" qilgan payitizda proektizdagi testlarni tekshirib boradi. Shunday qilip huddi shu narsani GitHub da ham qilsa boladi har bir push qilgan payitizda siz yozgan test lar boyicha tekshiradi agar testlardan otmasa "Actions" bolimida hatolikni korishiz munkin.
</p>

#### Buninb uchun ozizni proektizni ichida yangi papka yarating misoldagiday:
```.github/workflows/``` degan papka yarating ichida ```python-app.yml``` degan fayil yarating.

~~~yaml
## .github/workflows/python-app.yml
name: CI/CD Pipeline

on:
  push:
    branches:
      - main  # Change this to your main branch name

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: 3.8
# -----------------------------------------
    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt

    - name: Run tests
      run: |
        python -m pytest

~~~
### 'jobs' bolimida osizni proektizni yurgizish uchun terminalda qanday komandalarni kiritkan bolsangiz bundaham huddi shunday komandalar boladi batafsil molumotlar:
~~~yaml
# Birinchi nom beriladi:
name: "print Hello World"

# keyin komanda kiritiladi
run: | 
    chmod "Hello World!" 


~~~

## Rus tilidagi documentatsiya:

#### https://habr.com/ru/companies/otus/articles/530630/