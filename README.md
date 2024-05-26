## CI / CD nima va uni qanday ishlatish munkin ?
## <center> CI / CD o'zi nima? </center>

~~~txt
Ushbu turkum maqolalardan ko'zlangan asosiy maqsad, web servislarini reliz qilish jarayoni bilan qiynalayotgan, dasturning yangi imkoniyatlarni foydalanuvchilariga ishonchli va tez yetkazishda muammolarga duch kelayotgan jamoalar (team) uchun frontendda qo'llaniladigan keng tarqalgan amaliyotlarni jamlagan muxtasar qo'llanma sifatida yozildi. Maqoladagi ko'rsatmalar asosan kamida 2-4 kishilik jamoa bo'lib ishlayotgan frontend dasturchilar uchun qaratilgan bo'lsada, ba'zi umumiy tushunchalar backend developerlar uchun ham foydali bo'lishi mumkin. Ushbu post juda ko'plab men tanigan va shaxsan tanimagan dasturchilarning tajribalaridan kelib chiqib yozilganiga qaramay albatta xato va kamchiliklardan holi emas. Agar biron xato yoki kamchilik topsangiz albatta sharhlar bandida buni bildiring!
~~~
---
### CI / CD o`zi nima ?
~~~txt
Dasturiy ta'minotni reliz qilish, agar to'g'ri tashkil etilmasa, bosh-og'riq-beruvchi va ko'p vaqt talab qiladigan jarayon bo'lishi mumkin. Kodni reliz qilishga tayyor bo'lish bilan bog'liq vaqt majburiyatlari ya'ni deadlinelar ( savdo/marketing bo'limlari bosimi ostida) asab torlarini yanada taranglashtiradi. Buni hal qilishni oson yo'li bormi? Albatta bor, CI/CD 🚀
~~~
 + ~~~txt
    CI ya'ni Continuous Integration: dastur kodiga qo'shilgan har bir o'zgarishni (git commit) dastur kodi joylashgan 
    markaziy repositoryga avtomalashtirilgan shaklda davomiy qo'shib borish 
    CD ya'ni Continuous Delivery(Deployment): dastur kodini avtomalashtirilgan shaklda doimiy deploy qilish amaliyoti.
   ~~~

# Misol:
~~~
birobir proektiz bor u proektiz uchun test yozgansiz masalan: "pytest" moduli orqali --> "python -m pytest" qilgan payitizda proektizdagi testlarni tekshirib boradi. Shunday qilip huddi shu narsani GitHub da ham qilsa boladi har bir push qilgan payitizda siz yozgan test lar boyicha tekshiradi agar testlardan otmasa "Actions" bolimida hatolikni korishiz munkin.
~~~
#### Buninb uchun ozizni proektizni ichida yangi papka yarating misoldagiday:
```.github/workflows/```