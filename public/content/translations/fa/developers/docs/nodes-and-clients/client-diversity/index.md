---
title: تنوع کلاینت‌ها
description: توضیح سطح بالایی از اهمیت تنوع کلاینت در اتریوم.
lang: fa
sidebarDepth: 2
---

رفتار یک گره‌ی اتریوم توسط نرم‌افزار کلاینتی که اجرا می‌کند کنترل می‌شود. چندین کلاینت اتریوم در سطح تولید وجود دارند که هر کدام به زبان‌های مختلف توسط تیم‌های جداگانه توسعه یافته و نگهداری می‌شوند. کلاینت‌ها بر اساس مشخصات مشترکی ساخته شده‌اند که تضمین می‌کند کلاینت‌ها به‌طور یکپارچه با یکدیگر ارتباط برقرار می‌کنند و عملکرد یکسانی دارند و تجربه‌ی کاربری برابری را ارائه می‌دهند. با این حال، در حال حاضر توزیع کلاینت‌ها در سراسر گره‌ها به اندازه‌ی کافی برای تحقق این تقویت شبکه با پتانسیل کامل آن برابر نیست. در حالت ایده‌آل، کاربران تقریباً به‌طور مساوی بین کلاینت‌های مختلف تقسیم می‌کنند تا بیشترین تنوع کلاینت را به شبکه بیاورند.

## پیش‌نیازها {#prerequisites}

اگر از قبل نمی‌دانید گره‌ها و کاربرها چیست، [گره‌ها و کاربرها](/developers/docs/nodes-and-clients/) را بررسی کنید. لایه‌های [اجرا](/glossary/#execution-layer) و [اجماع](/glossary/#consensus-layer) در واژه‌نامه تعریف شده‌اند.

## چرا چندین کلاینت وجود دارد؟ {#why-multiple-clients}

کلاینت‌های متعددی وجود دارند که به‌طور مستقل توسعه یافته و نگهداری می‌شوند زیرا تنوع کلاینت شبکه را در برابر حملات و اشکال‌های نرم‌افزاری سرسخت‌تر می‌کند. تعدد کلاینت‌ها یک نقطه‌ی قوت منحصربه‌فرد برای اتریوم است - سایر زنجیره‌‌های بلوکی بر مصونیت یک کلاینت از خطای تکیه دارند. با این حال، صرفاً در دسترس داشتن چندین کلاینت کافی نیست، آن‌ها باید توسط جامعه پذیرفته شوند و کل گره‌های فعال به‌طور نسبتاً مساوی در بین آن‌ها توزیع شوند.

## چرا تنوع کلاینت مهم است؟ {#client-diversity-importance}

داشتن کلاینت‌های توسعه‌یافته به‌طور مستقل و نگهداری‌شده‌ی متعدد برای سلامت یک شبکه‌ی غیرمتمرکز حیاتی است. بیایید دلایل آن را بررسی کنیم.

### اشکالات نرم‌افزاری {#bugs}

یک اشکال در یک کلاینت منفرد که نماینده‌ی اقلیتی از گره‌های اتریوم باشد، خطر کمتری برای شبکه دارد. با توزیع تقریباً یکنواخت گره‌ها در بین بسیاری از کلاینت‌ها، احتمال اینکه اکثر کلاینت‌ها از یک مشکل مشترک رنج ببرند اندک است و در نتیجه شبکه قوی‌تر است.

### تاب‌آوری در برابر حملات {#resilience}

تنوع کلاینت همچنین باعث تاب‌آوری در برابر حملات می‌شود. به‌عنوان مثال، حمله ای که [یک کلاینت خاص را به سمت شاخه‌ی خاصی از زنجیره فریب دهد](https://twitter.com/vdWijden/status/1437712249926393858) بعید است موفقیت آمیز باشد زیرا بعید است سایر کلاینت‌ها به همان شیوه فریب بخورند و زنجیره‌ی متعارف خراب نمی‌شود. تنوع کم کلاینت، خطر مرتبط با هک در کلاینت غالب را افزایش می‌دهد. قبلاً ثابت شده است که تنوع کلاینت، دفاع مهمی در برابر حملات مخرب در شبکه است. به‌عنوان مثال، حمله‌ی محروم‌سازی از سرویس شانگهای در سال 2016 به این خاطر امکان‌پذیر بود که مهاجمان توانستند کلاینت غالب (Geth) را فریب دهند که یک دیسک آهسته‌ی عملیات i/o را ده‌ها هزار بار در هر بلوک اجرا کند. از آنجایی که کلاینت‌های جایگزین نیز آنلاین بودند و آسیب‌پذیری را نداشتند، اتریوم توانست در مقابل حمله مقاومت کند و تا زمانی که آسیب‌پذیری در Geth رفع شد، به کار خود ادامه دهد.

### قطعیت اثبات سهام {#finality}

یک باگ در یک کاربر توافقی با بیش از 33 درصد از گره‌های اتریوم می‌تواند از نهایی شدن لایه اجماع جلوگیری کند، به این معنی که کاربران نمی‌توانند اعتماد کنند که تراکنش‌ها در مقطعی بازگردانده یا تغییر نخواهند کرد. این برای بسیاری از برنامه های ساخته شده در بالای اتریوم، به ویژه DeFi، بسیار مشکل ساز خواهد بود.

<Emoji text="🚨" me="1rem" /> بدتر از آن، یک اشکال حیاتی در کلاینت با اکثریت دو سوم می‌تواند باعث شود که زنجیره <a href="https://www.symphonious.net/2021/09/23/what-happens-if-beacon-chain -consensus-fails/" target="_blank">به‌اشتباه تقسیم و نهایی شود</a>، که باعث می‌شود مجموعه‌ی بزرگی از اعتبارسنج‌ها در زنجیره‌ای نامعتبر گیر کنند. اگر بخواهند دوباره به زنجیره‌ی درست بپیوندند، این اعتبارسنج‌ها با برخورد شدید یا خروج و فعال‌سازی مجدد داوطلبانه‌ی آهسته و پرهزینه مواجه می‌شوند. شدت برخورد شدید متناسب با تعداد گره‌های مقصر است و دو سوم اکثریت مورد شدیدترین برخورد قرار می‌گیرند (32 اتر).

اگرچه این سناریوها بعید هستند، اما اکوسیستم اتریوم می‌تواند ریسک آن‌ها را با یکنواخت کردن توزیع کلاینت‌ها در سراسر گره‌های فعال کاهش دهد. در حالت ایده آل، هیچ کاربر اجماع هرگز به سهم 33% از کل گره ها نخواهد رسید.

### مسئولیت مشترک {#responsibility}

داشتن اکثریت کلاینت‌ها هزینه‌ی انسانی هم دارد. این کار، فشار و مسئولیت بیش از حدی بر دوش یک تیم توسعه‌ی کوچک وارد می‌کند. هرچه تنوع کلاینت کمتر باشد، بار مسئولیت توسعه‌دهندگانی که از کلاینت اکثریت نگهداری می‌کنند، بیشتر می‌شود. پخش کردن این مسئولیت بین تیم‌های متعدد، هم برای سلامت شبکه‌ی گره‌های اتریوم و هم برای شبکه‌ی افراد آن مفید است.

## تنوع کلاینت فعلی {#current-client-diversity}

![نمودار دایره‌ای که تنوع کلاینت را نشان می‌دهد](./client-diversity.png) _داده‌های نمودار از [ethernodes.org](https://ethernodes.org) و [ clientdiversity.org](https://clientdiversity.org/)_

دو نمودار دایره‌ای بالا تصاویری فوری از تنوع کلاینت فعلی برای لایه‌های اجرا و اجماع (در زمان نگارش در ژانویه 2022) را نشان می‌دهند. لایه‌ی اجرا غالباً در سلطه‌ی [Geth](https://geth.ethereum.org/) است، [Open Ethereum با فاصله دوم است،](https://openethereum.github.io/) [Erigon](https://github.com/ledgerwatch/erigon) سوم است و [Nethermind](https://nethermind.io/) چهارم است، و در عین حال سایر کلاینت‌ها که کمتر از 1% شبکه را تشکیل می‌دهند. رایج‌ترین کلاینت مورد استفاده در لایه‌ی اجماع - [Prysm](https://prysmaticlabs.com/#projects) - به اندازه Geth غالب نیست، اما در عین حال بیش از 60% از شبکه را نمایندگی می‌کند. [Lighthouse](https://lighthouse.sigmaprime.io/) و [Teku](https://consensys.net/knowledge-base/ethereum-2/teku/) به ترتیب 20% و حدود 14% حضور دارند و سایر کلاینت‌ها به‌ندرت استفاده می‌شوند.

داده های لایه اجرا از [Ethernodes](https://ethernodes.org) در 23 ژانویه 2022 به دست آمدند. داده‌های کلاینت‌های اجماع از [Michael Sproul](https://github.com/sigp/blockprint) گرفته شده است. به‌دست آوردن داده‌های کاربر اجماع دشوارتر است، زیرا کاربرهای لایه اجماع همیشه دارای ردپاهای واضحی نیستند که بتوان از آنها برای شناسایی استفاده کرد. داده‌ها با استفاده از یک الگوریتم طبقه‌بندی تولید شده‌اند که گاهی برخی از کلاینت‌های اقلیت را گیج می‌کند (برای جزئیات بیشتر به [اینجا](https://twitter.com/sproulM_/status/1440512518242197516) مراجعه کنید). در نمودار بالا، این طبقه‌بندی‌های مبهم یک برچسب یا این/یا آن (به‌عنوان مثال Nimbus/Teku) دارند. با وجود این، واضح است که اکثریتِ شبکه Prysm را اجرا می‌کند. داده‌ها، تصویری از مجموعه‌ی ثابتی از بلوک‌ها هستند (در این مورد، بلوک‌های بیکن در اسلات‌های 2048001 تا 2164916) و حضور غالب Prysm گاهی اوقات بالاتر و بیش از 68% بوده است. علی‌رغم صرفاً یک تصویر بودن، مقادیر نمودار درک کلی خوبی از وضعیت فعلی تنوع کلاینت ارائه می‌دهند.

داده های به روز شده تنوع مشتری، برای لایه اجماع اکنون در [clientdiversity.org](https://clientdiversity.org/) در دسترس است.

## لایه‌‌ی اجرا {#execution-layer}

تا به حال، گفتگو پیرامون تنوع کلاینت عمدتاً بر لایه‌ی اجماع متمرکز بوده است. با این حال، کلاینت اجرای [Geth](https://geth.ethereum.org) در حال حاضر حدود 85% از کل گره‌ها را تشکیل می‌دهد. این درصد به دلایل یکسان برای کلاینت‌های اجماع مشکل‌ساز است. برای مثال، یک اشکال نرم‌افزاری در Geth که روی انجام دادن تراکنش تأثیر می‌گذارد یا پی‌لودهای اجرایی درست می‌کند، می‌تواند منجر به این شود که کلاینت‌های اجماع تراکنش‌های مشکل‌ساز یا مشکل‌دار را نهایی کنند. بنابراین، اتریوم با توزیع یکنواخت‌تری از کلاینت‌های اجرایی سالم‌تر خواهد بود. حالت ایده‌آل این است که هیچ کلاینتی بیش از 33% از شبکه را نمایندگی نکند.

## از کلاینت اقلیت استفاده کنید {#use-minority-client}

توجه کردن به تنوع کلاینت به بیش از کاربران منفردی نیاز دارد که کلاینت‌های اقلیت را انتخاب کنند - این کار نیازمند استخرهای استخراج/ اعتبارسنج و نهادهایی مانند dappها و صرافی‌های اصلی است تا کلاینت‌ها را هم تغییر دهند. با این حال، همه‌ی کاربران می‌توانند سهم خود را در اصلاح عدم توازن فعلی و عادی‌سازی استفاده از تمام نرم‌افزارهای موجود اتریوم انجام دهند. پس از ادغام، تمام عملگرهای گره ملزم به اجرای یک کلاینت اجرا و یک کلاینت اجماع خواهند بود. انتخاب ترکیبی از کلاینت‌های پیشنهادشده در زیر به افزایش تنوع کلاینت کمک می‌کند.

### کلاینت‌های اجرا {#execution-clients}

[Besu](https://www.hyperledger.org/use/besu)

[Nethermind](https://downloads.nethermind.io/)

[Erigon](https://github.com/ledgerwatch/erigon)

[Go-Ethereum](https://geth.ethereum.org/)

### کلاینت‌های اجماع {#consensus-clients}

[Nimbus](https://nimbus.team/)

[Lighthouse](https://github.com/sigp/lighthouse)

[Teku](https://consensys.net/knowledge-base/ethereum-2/teku/)

[Lodestar](https://github.com/ChainSafe/lodestar)

[Prysm](https://docs.prylabs.network/docs/getting-started)

کاربران فنی می‌توانند با نوشتن آموزش‌ها و مستندات بیشتر برای کلاینت‌های اقلیت و تشویق همتایان گره‌گردان خود به مهاجرت کردن دور از کلاینت‌های غالب، به تسریع این فرایند کمک کنند. راهنماهای تغییر به کلاینت اجماع اقلیت در [clientdiversity.org](https://clientdiversity.org/) موجود است.

## داشبوردهای تنوع کلاینت {#client-diversity-dashboards}

چند داشبورد آمار تنوع کلاینت را به‌صورت لحظه‌ای برای لایه‌ی اجرا و اجماع ارائه می‌دهند.

**لایه‌ی اجماع:**

- [Rated.network](https://www.rated.network/)
- [clientdiversity.org](https://clientdiversity.org/) **لایه اجرا:**

- [supermajority.info](https://supermajority.info//)
- [Ethernodes](https://ethernodes.org/)

## اطلاعات بیشتر {#further-reading}

- [تنوع کلاینت در لایه‌ی اجماع اتریوم](https://mirror.xyz/jmcook.eth/S7ONEka_0RgtKTZ3-dakPmAHQNPvuj15nh0YGKPFriA)
- [ادغام اتریوم: کلاینت اکثریت را با ریسک خودتان اجرا کنید!](https://dankradfeist.de/ethereum/2022/03/24/run-the-majority-client-at-your-own-peril.html) - _دانکراد فیست، 24 مارس 2022_
- [اهمیت تنوع کلاینت](https://our.status.im/the-importance-of-client-diversity/)
- [فهرست خدمات گره‌ی اتریوم](https://ethereumnodes.com/)
- [«پنج چرا»ی مشکل تنوع کلاینت](https://notes.ethereum.org/@afhGjrKfTKmksTOtqhB9RQ/BJGj7uh08)
- [تنوع اتریوم و نحوه‌ حل آن (یوتیوب)](https://www.youtube.com/watch?v=1hZgCaiqwfU)
- [clientdiversity.org](https://clientdiversity.org/)

## موضوعات مرتبط {#related-topics}

- [اجرای یک گره‌ی اتریوم](/run-a-node/)
- [گره‌ها و کاربرها](/developers/docs/nodes-and-clients/)
