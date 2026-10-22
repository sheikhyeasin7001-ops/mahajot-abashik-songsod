# মহাজোট আবাসিক সংসদ — Website Starter

এই প্রজেক্টে responsive Bengali UI, Google Sign-In, সদস্য প্রোফাইল, Admin dashboard, কার্যকলাপের লগ, ঘটনা/কার্যবিবরণী, প্রস্তাব, ভোট এবং সম্মাননা আছে।

## গুরুত্বপূর্ণ
প্রজেক্টের কোড তৈরি আছে, কিন্তু এটি এখনো প্রকাশিত live website নয়। বাস্তব Google লগইন ও online shared database চালু করতে Firebase project তৈরি করে নিচের সেটআপ সম্পন্ন করতে হবে। Firebase credentials বা hosting account ছাড়া আমি তোমার হয়ে বাইরের account-এ deploy করতে পারি না।

## Firebase সেটআপ
1. https://console.firebase.google.com/ এ Google account দিয়ে sign in করো।
2. Add project দিয়ে project বানাও, যেমন `mahajot-abashik-songsod`.
3. Project settings > General > Your apps থেকে Web app যোগ করে Firebase config সংগ্রহ করো।
4. Authentication > Sign-in method-এ Google provider enable করো।
5. Firestore Database তৈরি করো।
6. এই ZIP-এর `index.html`-এ তোমার দেওয়া Firebase config ইতিমধ্যে বসানো আছে; আর বসাতে হবে না।
7. Firebase Console > Firestore > Rules-এ `firestore.rules`-এর content paste করে Publish করো।
8. Hosting-এর জন্য Firebase CLI install করে terminal-এ project folder-এ:
   - `npm install -g firebase-tools`
   - `firebase login`
   - `firebase init hosting firestore` (existing `firebase.json` ও rules ব্যবহার করো)
   - `firebase deploy`

## Admin
Admin email: `sheikh.yeasin7001@gmail.com`

এই ইমেইলে Google Sign-In করতে হবে। Firestore rules-এ একই ইমেইল Admin হিসেবে নির্ধারিত। নিজের Gmail-এ Google Sign-In চালু আছে নিশ্চিত করো।

## কার্যকলাপ ও privacy
Admin সদস্যদের email, সর্বশেষ login এবং এই সাইটের ভেতরে লগ করা কাজ দেখতে পারবেন। লগ করা কাজের উদাহরণ: login/logout, ঘটনা/প্রস্তাব/ভোট/সম্মাননা তৈরি, ভোট দেওয়া। এটি অন্য অ্যাপ, বাইরের browsing, ব্যক্তিগত ফাইল বা পাসওয়ার্ড ট্র্যাক করে না। সদস্যদের activity logging সম্পর্কে আগে জানিয়ে নাও।

## Production-এর আগে
- Firebase config বসাও, Firestore rules publish করো।
- Hosting-এর authorized domains-এ live domain যোগ করো।
- ভোটের নিয়ম ও একবার ভোট দেওয়ার সীমা production-এর জন্য আরও শক্ত করো; এই starter UI-এর ভোট ব্যবস্থা উন্নত করার জায়গা আছে।
- Firebase App Check ও abuse protection চালু করো।
- Google font-এর জন্য internet connection প্রয়োজন; font না এলে fallback system font ব্যবহৃত হবে।
