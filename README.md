
**هذه الملفات مبنية من المهندس أحمد برناوي لتطوير أنظمة القيادة لهيونداي , كيا , جينسس**


https://github.com/xx979xx/openpilot

إنه مفتوح المصدر ومرخص من معهد ماساتشوستس للتكنولوجيا. بتثبيت هذا البرنامج ، فإنك تتحمل كامل المسؤولية عن أي شيء قد يحدث أثناء استخدامه. جميع المساهمين في هذه الشركة غير مسؤولين. استخدمه على مسؤوليتك الخاصة.

------------------------------------------------------


![](https://i.imgur.com/JVj5aZc.jpg)

جدول المحتويات
=======================

* [ماهو برنامج الاوبن بايلوت ؟](#what-is-openpilot)
* [عمله على السيارة](#running-in-a-car)
* [عمله على الكمبيوتر](#running-on-pc)
* [المجتمع والمساهمة](#community-and-contributing)
* [بينانات المسخدم وحساب كوما](#user-data-and-comma-account)
* [السلامة والاختبار](#safety-and-testing)
* [بنية الدليل](#directory-structure)
* [الترخيص](#licensing)

---

ماهو الأوبن بايلوت؟
------

[openpilot](http://github.com/commaai/openpilot) هو نظام مفتوح المصدر لمساعدة السائق. حاليًا ، يؤدي برنامج openpilot وظائف التحكم التكيفي في القيادة (ACC) ، وتمركز المسار الآلي (ALC) ، والتحذير من الاصطدام الأمامي (FCW) ، والتحذير من مغادرة المسار (LDW) لمجموعة متزايدة من [السيارات المدعومة والموديلات الحديثة كل عام](docs/CARS.md). بالإضافة أثناء تشغيل الأوبن بايلوت , تعمل كاميرا مراقبة السائق (DM) على مراقبة السائق المشتت الإنتباه والنائم أثناء عمل النظام. لمزيد من المعلومات [ تكامل المركبة ](docs/INTEGRATION.md) و [محدودية](docs/LIMITATIONS.md).

<table>
  <tr>
    <td><a href="https://youtu.be/Asq9IBZ5EL8" title="Video By Greer Viau"><img src="https://i.imgur.com/1aVz6fu.png"></a></td>
    <td><a href="https://youtu.be/YfMKV0BCS3E" title="Video By Logan LeGrand"><img src="https://i.imgur.com/U2kBp1r.jpg"></a></td>
    <td><a href="https://youtu.be/fE3jcvNPKuU" title="Video By Charlie Kim"><img src="https://i.imgur.com/PInrzIG.jpg"></a></td>
    <td><a href="https://youtu.be/-IkImTe1NYE" title="Video By Aragon"><img src="https://i.imgur.com/04VNzPf.jpg"></a></td>
  </tr>
  <tr>
    <td><a href="https://youtu.be/iIUICQkdwFQ" title="Video By Logan LeGrand"><img src="https://i.imgur.com/b1LHQTy.jpg"></a></td>
    <td><a href="https://youtu.be/XOsa0FsVIsg" title="Video By PinoyDrives"><img src="https://i.imgur.com/6FG0Bd8.jpg"></a></td>
    <td><a href="https://youtu.be/bCwcJ98R_Xw" title="Video By JS"><img src="https://i.imgur.com/zO18CbW.jpg"></a></td>
    <td><a href="https://youtu.be/BQ0tF3MTyyc" title="Video By Tsai-Fi"><img src="https://i.imgur.com/eZzelq3.jpg"></a></td>
  </tr>
</table>


عمله على السيارة
------

لاستخدام نظام الاوبن بايلوت تحتاج إلى أربعة أشياء.
* هذا البرنامج إنه مجاني ومتاح هنا.
* إحدى[ أكثر من 150 سيارة مدعومة ](docs/CARS.md). نحن ندعم هوندا, تويوتا ، هيونداي ، نيسان ، كيا ، كرايسلر ، لكزس ، أكورا ، أودي ، فولكس فاجن ، وأكثر من ذلك. إذا كانت سيارتك غير مدعومة, ولاكن يجب أن يكون لديك نظام مثبت السرعة التكيفي ومساعد الحفاظ على المسار لكي تستطيع تشغيل نظام الاوبن بايلوت على مركبتك.
* الجهاز يدهم تشعيل البرنامج[كوما إثنين](https://comma.ai/shop/products/two), [كوما ثلاثة](https://comma.ai/shop/products/three), أو إذا كنت ترغب في التجربة, على [اليوبينتو مع كاميرا الويب](https://github.com/commaai/openpilot/tree/master/tools/webcam).
* طريقة التوصيل مع سيارتك على كوما إثنين أو ثلاثة تحتاج فقط إلى [ظفيرة للتوصيل](https://comma.ai/shop/products/car-harness). مع الايون الذهبي أو الكمبيوتر وأيضاً تحتاج إلى [البلاك باندا ] (https://comma.ai/shop/products/panda).
 لدينا إرشادات مفصلة حول [كيفية تثبيت الجهاز في السيارة](https://comma.ai/setup).

العمل على جهاز الكمبيوتر
--------

يمكن تشغيل جميع خدمات الأوبن بايلوت كالمعتاد على جهاز الكمبيوتر , حتى بدون أجهزة خاصة أو سيارة لتطوير أو تجربة الأوبن بايلوت , زيمكن تشغيل الأوبن بايلوت على بيانات مسجلة أو محاكاة.

بإستخدام أدوات الأوبن بايلوت , يمكنك رسم السجلات , وإعادة تشغيل محركات الأقراص ومشاهدة تدفقات الكاميرا كاملة الدقة , انظر [ معلومات الأدوات ] (tools/README.md). 
يمكنك أيضاً تشغيل الأوبن بايلوت على المحاكي [ على محاكي كلارا ] (tools/sim/README.md).  
(tools/sim/README.md). This allows openpilot to drive around a virtual car on your Ubuntu machine. The whole setup should only take a few minutes, but does require a decent GPU.


المجتمع والمساهمة
------

openpilot is developed by [comma](https://comma.ai/) and by users like you. We welcome both pull requests and issues on [GitHub](http://github.com/commaai/openpilot). Bug fixes and new car ports are encouraged. Check out [the contributing docs](docs/CONTRIBUTING.md).

Documentation related to openpilot development can be found on [docs.comma.ai](https://docs.comma.ai). Information about running openpilot (e.g. FAQ, fingerprinting, troubleshooting, custom forks, community hardware) should go on the [wiki](https://github.com/commaai/openpilot/wiki).

You can add support for your car by following guides we have written for [Brand](https://blog.comma.ai/how-to-write-a-car-port-for-openpilot/) and [Model](https://blog.comma.ai/openpilot-port-guide-for-toyota-models/) ports. Generally, a car with adaptive cruise control and lane keep assist is a good candidate. [Join our Discord](https://discord.comma.ai) to discuss car ports: most car makes have a dedicated channel.

Want to get paid to work on openpilot? [comma is hiring](https://comma.ai/jobs/).

And [follow us on Twitter](https://twitter.com/comma_ai).

User Data and comma Account
------

By default, openpilot uploads the driving data to our servers. You can also access your data through [comma connect](https://connect.comma.ai/). We use your data to train better models and improve openpilot for everyone.

openpilot is open source software: the user is free to disable data collection if they wish to do so.

openpilot logs the road facing cameras, CAN, GPS, IMU, magnetometer, thermal sensors, crashes, and operating system logs.
The driver facing camera is only logged if you explicitly opt-in in settings. The microphone is not recorded.

By using openpilot, you agree to [our Privacy Policy](https://comma.ai/privacy). You understand that use of this software or its related services will generate certain types of user data, which may be logged and stored at the sole discretion of comma. By accepting this agreement, you grant an irrevocable, perpetual, worldwide right to comma for the use of this data.

Safety and Testing
----

* openpilot observes ISO26262 guidelines, see [SAFETY.md](docs/SAFETY.md) for more details.
* openpilot has software in the loop [tests](.github/workflows/selfdrive_tests.yaml) that run on every commit.
* The code enforcing the safety model lives in panda and is written in C, see [code rigor](https://github.com/commaai/panda#code-rigor) for more details.
* panda has software in the loop [safety tests](https://github.com/commaai/panda/tree/master/tests/safety).
* Internally, we have a hardware in the loop Jenkins test suite that builds and unit tests the various processes.
* panda has additional hardware in the loop [tests](https://github.com/commaai/panda/blob/master/Jenkinsfile).
* We run the latest openpilot in a testing closet containing 10 comma devices continuously replaying routes.

بنية الدليل
------
    .
    ├── cereal              # مواصفات الرسائل و الطبقات المستخدمة في جميع الخوارزميات
    ├── common              # مكتبة مثل الوظائف التي قمنا بتطويرها هنا
    ├── docs                # التوثيق
    ├── opendbc             # ملفات توضح كيفية تفسير البيانات من السيارات
    ├── panda               # رمز يستخدم للتواصل على الكان
    ├── third_party         # مكتبات خارجية
    ├── pyextra             # حزم بايثون الإضافية
    └── selfdrive           # الأكواد المطلوبة لقيادة السيارة
        ├── assets          # الخطوط, الصور, و الأصوات للواجهة
        ├── athena          # يسمح بالتواصل مع التطبيق
        ├── boardd          # الديمون الذي يسمح للاتصال مع البورد
        ├── camerad         # يسمح لالتقاط الصور من مستشعرات الكاميرا
        ├── car             # رمز السيارة المحدد لقراءة الحالات والتحكم في المشغلات
        ├── common          # كود C / C ++ مشترك الدومين
        ├── controls        # التخطيط والضوابط
        ├── debug           # أدوات لمساعدتك على التصحيح والقيام بمنافذ السيارة
        ├── locationd       # توطين دقيق وتقدير معايرة السيارة
        ├── logcatd         # ملفات الأندرويد والخدمات
        ├── loggerd         # مسجل وتحميل بيانات السيارة
        ├── modeld          # نظام مراقبة القيادة أثناء العمل
        ├── proclogd        # معلومات السجلات من proc
        ├── sensord         # رمز واجهة IMU
        ├── test            # اختبارات الوحدة واختبارات النظام وجهاز محاكاة السيارة
        └── ui              # واجهة المستخدم

Licensing
------

openpilot is released under the MIT license. Some parts of the software are released under other licenses as specified.

Any user of this software shall indemnify and hold harmless Comma.ai, Inc. and its directors, officers, employees, agents, stockholders, affiliates, subcontractors and customers from and against all allegations, claims, actions, suits, demands, damages, liabilities, obligations, losses, settlements, judgments, costs and expenses (including without limitation attorneys’ fees and costs) which arise out of, relate to or result from any use of this software by user.

**THIS IS ALPHA QUALITY SOFTWARE FOR RESEARCH PURPOSES ONLY. THIS IS NOT A PRODUCT.
YOU ARE RESPONSIBLE FOR COMPLYING WITH LOCAL LAWS AND REGULATIONS.
NO WARRANTY EXPRESSED OR IMPLIED.**

---

<img src="https://d1qb2nb5cznatu.cloudfront.net/startups/i/1061157-bc7e9bf3b246ece7322e6ffe653f6af8-medium_jpg.jpg?buster=1458363130" width="75"></img> <img src="https://cdn-images-1.medium.com/max/1600/1*C87EjxGeMPrkTuVRVWVg4w.png" width="225"></img>

[![openpilot tests](https://github.com/commaai/openpilot/workflows/openpilot%20tests/badge.svg?event=push)](https://github.com/commaai/openpilot/actions)
[![Total alerts](https://img.shields.io/lgtm/alerts/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/alerts/)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/context:python)
[![Language grade: C/C++](https://img.shields.io/lgtm/grade/cpp/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/context:cpp)
[![codecov](https://codecov.io/gh/commaai/openpilot/branch/master/graph/badge.svg)](https://codecov.io/gh/commaai/openpilot)
