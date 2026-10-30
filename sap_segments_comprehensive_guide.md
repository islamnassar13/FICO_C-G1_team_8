# الدليل المرجعي الشامل لمفهوم القطاعات (Segments) في SAP General Ledger و S/4HANA

## دليل التمييز اللوني المعتمد في GitHub (Color-Coding Legend)

تم تصميم هذا المستند باستخدام **صناديق التنبيه اللونية الأصلية في GitHub (GitHub Native Colored Alerts)** بدون أي أكواد HTML خارجية، ليظهر التمييز اللوني بشكل نظيف واحترافي:

| نوع المحتوى | المؤشر البصري | تنسيق GitHub الرسمي | اللون الظاهر في GitHub | الوصف |
| :--- | :--- | :--- | :--- | :--- |
| **كلام الكاتب الأصلي (Paul Ovigele)** | 🟦 **[النص الأصلي - المؤلف]** | `> [!NOTE]` | **الأزرق (Blue `Note` Box)** | النص الإنجليزي الأصلي كاملاً حرفياً دون حذف أو تعديل أي حرف، متبوعاً بترجمته الدقيقة. |
| **الإضافات والتحليل المعماري والإثراء** | 🟩 **[إثراء وتحليل معمق]** | `> [!TIP]` | **الأخضر (Green `Tip` Box)** | الشرح التفصيلي، منطق SAP، منطق البيزنس، المعايير المحاسبية، والأثر على جميع الموديولات. |
| **الخلاصات والضوابط الاستشارية الحرجة** | 🟪 **[قاعدة استشارية هامة]** | `> [!IMPORTANT]` | **البنفسجي (Purple `Important` Box)** | القواعد الذهبية، التحذيرات التنفيذية، ومصفوفة اتخاذ القرار للمشاريع. |

## القسم الأول: النص الأصلي الكامل للمؤلف (حرفياً دون انتقاص حرف واحد)

> [!NOTE]
> 🟦 **[النص الأصلي الكامل كما كتبه Paul Ovigele حرفياً دون تعديل أو نقصان]**
>
> The Purpose of Segments in SAP General Ledger
> Posted by Paul Ovigele
>
> STANDARD OF LVING
>
> Even if you have read the SAP Help notes, attended conferences and Webinars, talked to experts and
> searched Google every now and then, I wouldn't be surprised if you still were not clear on the exact
> purpose of Segments.
>
> Let me try to provide some clarity on this topic. Note that I am not speaking on behalf of SAP or anyone
> else, just on my experience with several clients and the putting together of information that I have
> garnered from the various sources mentioned above.
>
> First of all let us look at the definition of Segment by SAP:
>
> "Division of a company for which you can create financial statements for external reporting"
>
> This concept was introduced by SAP to satisfy the requirement by the Securities and Exchange
> Commission (S.E.C.) in the United States and the International Accounting Standards Board (IASB),
> which stipulates that companies should report financial information by business or geographic area.
>
> In SAP, the one guaranteed way of creating full financial statements, is to set up the segment as a
> company code. However, this would mean that company codes would need to be created for each
> business segment, some which themselves will span several company codes. This could lead to a rather
> cumbersome and complex set up of the company code structure.
>
> Two existing SAP objects could go some way to facilitating the production of financial statements. They
> are as follows:
>
> (1) Business Areas: This is the division of a company for which you can create financial statements for
> external reporting. By definition, this seems to satisfy the requirement specified by the SEC and IASB.
> However, for the past decade, there has been talk in SAP circles, that Business Areas will cease to be
> supported by SAP in the future (at what point in the future this will happen, is left to be seen);
>
> (2) Profit centers: This is an organizational unit in accounting that reflects a management-oriented
> structure of the organization for the purpose of internal control. Profit Centers have transitioned through the years from being part of the Controlling module (for Profit and Loss Management reporting) to being
> part of the Enterprise Controlling module (for P&L as well as certain Balance sheet items) to being part of
> the general ledger (for full financial statement reporting using document splitting).
>
> A question that I have been asked several times is, since there are already two objects that can be used
> to create financial statements (albeit partially), then why did SAP introduce a brand new object (i.e.
> Segments) to satisfy the segment reporting requirement.
>
> The answer that I found is that most SAP customers are using Profit centers and Business areas for other
> purposes (for example, I have seen clients using profit centers as cost centers, plants, or Sales areas)
> and therefore it may be difficult to switch these objects to full financial statement reporting entities. This is
> particularly relevant in cases where companies have hundreds (or even thousands) of Profit
> Centers/Business Areas. This is why segments have been introduced so that you can have a brand new
> object which can be used solely for "Segment" reporting.
>
> One thing that I caution clients about is that they should not think that Segment reporting can only be
> satisfied by the use of segments. In fact, if you are carrying out a brand new SAP implementation I
> recommend that you use profit centers (along with document splitting functionality) for segment reporting.
> I would leave business areas alone, if you are a new company, since (as mentioned above) the future of
> this functionality is still uncertain.

## القسم الثاني: التفكيك التحليلي الفقري (نص المؤلف بالأزرق مقابل الإثراء المعمق بالأخضر)

### 1. إشكالية الغموض حول مفهوم الـ Segment في مجتمع SAP

> [!NOTE]
> 🟦 **[كلام الكاتب الأصلي - الفقرة 1 و 2]**
>
> **The Purpose of Segments in SAP General Ledger**
> **Posted by Paul Ovigele**
>
> **STANDARD OF LVING**
>
> **Even if you have read the SAP Help notes, attended conferences and Webinars, talked to experts and searched Google every now and then, I wouldn't be surprised if you still were not clear on the exact purpose of Segments.**
>
> **Let me try to provide some clarity on this topic. Note that I am not speaking on behalf of SAP or anyone else, just on my experience with several clients and the putting together of information that I have garnered from the various sources mentioned above.**
>
> **الترجمة الدقيقة لكلام المؤلف:**
> حتى لو كنت قد قرأت ملاحظات مساعدة SAP (SAP Help notes)، وحضرت المؤتمرات والندوات عبر الإنترنت، وتحدثت إلى الخبراء وبحثت في Google بين الحين والآخر، فلن أتفاجأ إذا كنت لا تزال غير متأكد من الغرض الدقيق للقطاعات (Segments). دعني أحاول تقديم بعض الوضوح حول هذا الموضوع، علماً بأنني لا أتحدث نيابةً عن SAP أو أي جهة أخرى، بل انطلاقاً من خبرتي مع عدة عملاء وتجميعي للمعلومات التي استقيتها من المصادر المختلفة المذكورة أعلاه.

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - لماذا يكتنف الغموض مفهوم الـ Segment؟]**
>
> **جذور الالتباس بين المنظور التقني والمنظور المحاسبي:**
> يرجع الغموض الذي أشار إليه Paul Ovigele إلى تداخل ثلاثة مفاهيم في بيئة SAP تشترك جميعها في القدرة على إصدار قوائم مالية جزئية أو كلية، وهي: **Business Area (`GSBER`)**، و **Profit Center (`PRCTR`)**، و **Segment (`SEGMENT`)**.
>
> * **منطق SAP التقني (SAP System Logic):** ظهر كائن الـ `Segment` مع إطلاق **SAP ERP 6.0 (New General Ledger - New G/L)** كحقل أصيل في جدول الأستاذ العام `FAGLFLEXA` و `FAGLFLEXT`، ثم أصبح لاحقاً ركيزة أساسية في جدول القيود الموحد **Universal Journal (`ACDOCA`)** في **SAP S/4HANA**. تقنياً، لا يُشتق الـ Segment بشكل مباشر من فراغ، بل يرتبط عضوياً في البيانات الأساسية (Master Data) بمركز الربحية (**Profit Center Master Record - KE51/KE52**) ليتم وراثته تلقائياً (Derivation) أثناء الترحيل المحاسبي.
> * **منطق البيزنس (Business Logic):** الشركات المساهمة الكبرى التي تعمل في أنشطة متعددة (مثل مجموعة تعمل في التطوير العقاري، الصناعات الغذائية، والخدمات اللوجستية) لا يُقنع المساهمين أو هيئات سوق المال فيها رؤية ميزانية مجمعة واحدة للشركة؛ بل يحتاج المستثمر لمعرفة: أي قطاع يولّد التدفقات النقدية؟ وأي قطاع يستنزف الأصول؟ وأي قطاع يتحمل الالتزامات الأكبر؟

### 2. التعريف الرسمي والمرجعية التنظيمية الدولية (SEC & IASB)

> [!NOTE]
> 🟦 **[كلام الكاتب الأصلي - الفقرة 3 و 4 و 5]**
>
> **First of all let us look at the definition of Segment by SAP:**
>
> **"Division of a company for which you can create financial statements for external reporting"**
>
> **This concept was introduced by SAP to satisfy the requirement by the Securities and Exchange Commission (S.E.C.) in the United States and the International Accounting Standards Board (IASB), which stipulates that companies should report financial information by business or geographic area.**
>
> **الترجمة الدقيقة لكلام المؤلف:**
> أولاً دعونا نلقي نظرة على تعريف الـ Segment من قِبل SAP: «قسم من الشركة يمكنك من أجله إنشاء قوائم مالية لأغراض التقارير الخارجية». تم تقديم هذا المفهوم بواسطة SAP لتلبية متطلبات هيئة الأوراق المالية والبورصات (S.E.C.) في الولايات المتحدة ومجلس معايير المحاسبة الدولية (IASB)، والتي تنص على أنه يجب على الشركات الإبلاغ عن المعلومات المالية حسب قطاع الأعمال أو المنطقة الجغرافية.

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - الأبعاد المحاسبية والتنظيمية: IFRS 8 و ASC 280]**
>
> **التأصيل المعياري للمتطلبات القانونية التي صُمم الـ Segment لأجلها:**
>
> 1. **المعيار الدولي لإعداد التقارير المالية (IFRS 8 - Operating Segments) الصادر عن IASB (والذي حل محل IAS 14):**
>    يلزم الشركات المدرجة بالإفصاح عن القطاعات التشغيلية بناءً على **نهج الإدارة (Management Approach)**، أي بنفس الطريقة التي يراجع بها متخذ القرار التشغيلي الرئيسي (**CODM - Chief Operating Decision Maker**) الأداء لتخصيص الموارد وتقييم الربحية.
> 2. **معيار المحاسبة الأمريكي (US GAAP ASC 280 - Segment Reporting) المعتمد لدى هيئة SEC:**
>    يشترط الإفصاح عن الأرباح والخسائر، والأصول الكلية، والالتزامات، والمصروفات الرأسمالية لكل قطاع تشغيلي يتجاوز **عتبة الأهمية النسبية (10% Quantitative Threshold Rule)** من حيث:
>    * **معيار الإيرادات:** إيرادات القطاع (الداخلية والخارجية) تساوي أو تتجاوز 10% من إجمالي إيرادات كافة القطاعات.
>    * **معيار الأرباح أو الخسائر:** القيمة المطلقة لربح أو خسارة القطاع تساوي أو تتجاوز 10% من إجمالي أرباح القطاعات الرابحة أو خسائر القطاعات الخاسرة (أيهما أكبر).
>    * **معيار الأصول:** أصول القطاع تساوي أو تتجاوز 10% من إجمالي أصول جميع القطاعات التشغيلية.
> 3. **قاعدة الـ 75% للإيرادات الخارجية:**
>    يجب أن تغطي القطاعات المفصح عنها خارجياً ما لا يقل عن **75% من إجمالي إيرادات الشركة الخارجية**، وإلا وجب إضافة قطاعات إضافية حتى لو لم تبلغ نسبة الـ 10%.
> 4. **ماذا يعني "قوائم مالية كاملة (Full Financial Statements)" في منطق SAP؟**
>    يعني القدرة على استخراج:
>    * **قائمة المركز المالي المتوازنة (Balanced Balance Sheet):** حيث تتساوى (الأصول = الالتزامات + حقوق الملكية) على مستوى الـ Segment الواحد بفضل خاصية **Document Splitting** وحساب التسوية الصفرية (**Zero-Balance Clearing Account**).
>    * **قائمة الدخل (Profit & Loss Statement):** إيرادات ومصروفات القطاع.

### 3. إشكالية استخدام كود الشركة (Company Code) كقطاع

> [!NOTE]
> 🟦 **[كلام الكاتب الأصلي - الفقرة 6]**
>
> **In SAP, the one guaranteed way of creating full financial statements, is to set up the segment as a company code. However, this would mean that company codes would need to be created for each business segment, some which themselves will span several company codes. This could lead to a rather cumbersome and complex set up of the company code structure.**
>
> **الترجمة الدقيقة لكلام المؤلف:**
> في SAP، الطريقة الوحيدة المضمونة تقليدياً لإنشاء قوائم مالية كاملة هي إعداد القطاع ككود شركة (Company Code). ومع ذلك، فإن هذا يعني أنه سيتعين إنشاء أكواد شركات لكل قطاع أعمال، وبعض هذه القطاعات نفسها قد يمتد عبر عدة أكواد شركات، مما قد يؤدي إلى إعداد مرهق ومعقد للغاية لهيكل أكواد الشركات.

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - لماذا يفشل Company Code في تمثيل الـ Segment؟]**
>
> **المقارنة المعمارية بين الكيان القانوني والقطاع التشغيلي:**
>
> * **منطق البيزنس والقانون:** الـ **Company Code (`BUKRS`)** في SAP يمثل **كياناً قانونياً مستقلاً (Independent Legal Entity)** له سجل تجاري، بطاقة ضريبية، وحسابات بنكية باسمه القانوني. أما الـ **Segment** فهو **بُعد عمل (Business Line Dimension)** قد يعبر الحدود القانونية والجغرافية (**Cross-Company Code**).
> * **مثال عملي من الواقع:** شركة قابضة لديها كيانان قانونيان: `Company Code 1000` في مصر و `Company Code 2000` في السعودية. كلا الكيانين يعملان في نشاطين: **قطاع البتروكيماويات (Segment A)** و **قطاع الأسمدة (Segment B)**.
>   * لو حاولنا تطبيق فكرة إنشاء Company Code لكل قطاع، لاضطررنا لإنشاء 4 أكواد شركات بدلاً من 2، مما يؤدي إلى:
>     1. تضاعف قيود المعاملات البينية (**Intercompany Transactions - OBYA**) داخل نفس الدولة الواحدة!
>     2. تعقيد الإقرارات الضريبية (VAT / Withholding Tax) التي تشترطها الدولة على مستوى السجل التجاري الواحد وليس على مستوى خطوط الإنتاج.
>     3. تضخم البيانات الأساسية للعملاء والموردين (`Customer/Vendor Company Code Views - KNB1/LFB1`) والحسابات البنكية.

### 4. البدائل التاريخية في SAP: مناطق الأعمال (Business Areas) ومراكز الربحية (Profit Centers)

> [!NOTE]
> 🟦 **[كلام الكاتب الأصلي - الفقرة 7 و 8 و 9]**
>
> **Two existing SAP objects could go some way to facilitating the production of financial statements. They are as follows:**
>
> **(1) Business Areas: This is the division of a company for which you can create financial statements for external reporting. By definition, this seems to satisfy the requirement specified by the SEC and IASB. However, for the past decade, there has been talk in SAP circles, that Business Areas will cease to be supported by SAP in the future (at what point in the future this will happen, is left to be seen);**
>
> **(2) Profit centers: This is an organizational unit in accounting that reflects a management-oriented structure of the organization for the purpose of internal control. Profit Centers have transitioned through the years from being part of the Controlling module (for Profit and Loss Management reporting) to being part of the Enterprise Controlling module (for P&L as well as certain Balance sheet items) to being part of the general ledger (for full financial statement reporting using document splitting).**
>
> **الترجمة الدقيقة لكلام المؤلف:**
> هناك كائنان موجودان مسبقاً في SAP يمكنهما المساهمة إلى حد ما في تسهيل إنتاج القوائم المالية، وهما كالتالي:
> (1) **مناطق الأعمال (Business Areas):** هي قسم من الشركة يمكنك من أجله إنشاء قوائم مالية للتقارير الخارجية. ومن حيث التعريف، يبدو أن هذا يلبي المتطلبات المحددة من قِبل SEC و IASB. ومع ذلك، على مدار العقد الماضي، كان هناك حديث في أوساط SAP بأن مناطق الأعمال سيتوقف دعمها من قِبل SAP في المستقبل (ومتى سيحدث ذلك في المستقبل هو أمر متروك للأيام).
> (2) **مراكز الربحية (Profit Centers):** هي وحدة تنظيمية في المحاسبة تعكس هيكلاً موجهاً نحو الإدارة للمؤسسة لغرض الرقابة الداخلية. وقد انتقلت مراكز الربحية عبر السنين من كونها جزءاً من موديول التكاليف Controlling (لتقارير إدارة الأرباح والخسائر) إلى كونها جزءاً من موديول الرقابة المؤسسية Enterprise Controlling (للأرباح والخسائر بالإضافة إلى بنود معينة في الميزانية العمومية) وصولاً إلى كونها جزءاً من الأستاذ العام General Ledger (لإعداد تقارير القوائم المالية الكاملة باستخدام تقسيم المستندات Document Splitting).

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - التطور التاريخي والمعماري من R/3 إلى S/4HANA]**
>
> **أولاً: لماذا تراجعت مكانة Business Area (`GSBER`)؟**
> * في عصر **SAP R/3 (Classic G/L)**، كانت `Business Area` هي الأداة الوحيدة في FI لاستخراج ميزانية فرعية عبر أكواد الشركات (بمساعدة التسويات الدورية في آخر الشهر `F.5D` و `F.5E`).
> * غير أن `Business Area` كانت تعاني من **ضعف الاشتقاق التلقائي (Weak Derivation)**؛ فالمستخدم كان يضطر لإدخالها يدوياً في كثير من القيود، ولم تكن مرتبطة عضوياً بهرمية مراكز التكلفة بنفس قوة Profit Center.
> * في **SAP S/4HANA**، ورغم بقاء الحقل `GSBER` في جدول `ACDOCA` لأغراض التوافق مع الأنظمة القديمة (Backward Compatibility)، فإن توصيات SAP الرسمية في **Simplification List** تعتبر `Business Area` تقنية متقادمة (Deprecated Concept) لحساب الثنائي الأقوى: **Profit Center + Segment**.
>
> **ثانياً: المراحل التاريخية الأربع لتطور Profit Center (`PRCTR`) في SAP:**
> 1. **المرحلة الأولى (CO-PCA الكلاسيكي):** أداة تحليلية داخل موديول CO تركز على قائمة الدخل (الإيرادات والمصروفات التشغيلية) فقط.
> 2. **المرحلة الثانية (EC-PCA - Enterprise Controlling):** دفتر أستاذ مستقل بذاته (بياناته مخزنة في جداول منفصلة مثل `GLPCA` و `GLPCT`) يسمح بنقل بعض بنود الميزانية (الأصول الثابتة، المخزون، الذمم المدينة والدائنة) عبر برامج ترحيل آخر الشهر (`1KEH`, `1KEI`, `1KEK`)، لكنه كان يسبب **فجوة مطابقة (Reconciliation Gap)** بين FI و EC-PCA.
> 3. **المرحلة الثالثة (SAP ERP 6.0 - New G/L):** دمج الـ Profit Center والـ Segment مباشرة داخل جداول الأستاذ العام (`FAGLFLEXA`) مع ابتكار محرك **Document Splitting** اللحظي (Real-time)، مما ألغى الحاجة لتسويات نهاية الشهر لتقسيم الميزانية.
> 4. **المرحلة الرابعة (SAP S/4HANA - Universal Journal `ACDOCA`):** توحيد FI و CO و AA و ML في جدول واحد هو `ACDOCA` (المعروف بـ **Single Source of Truth**)، حيث يتواجد كل من `PRCTR` و `SEGMENT` في كل سطر قيد محاسبي لحظياً.

### 5. السؤال الجوهري: لماذا ابتكرت SAP كائن الـ Segment رغم وجود البديلين؟

> [!NOTE]
> 🟦 **[كلام الكاتب الأصلي - الفقرة 10 و 11]**
>
> **A question that I have been asked several times is, since there are already two objects that can be used to create financial statements (albeit partially), then why did SAP introduce a brand new object (i.e. Segments) to satisfy the segment reporting requirement.**
>
> **The answer that I found is that most SAP customers are using Profit centers and Business areas for other purposes (for example, I have seen clients using profit centers as cost centers, plants, or Sales areas) and therefore it may be difficult to switch these objects to full financial statement reporting entities. This is particularly relevant in cases where companies have hundreds (or even thousands) of Profit Centers/Business Areas. This is why segments have been introduced so that you can have a brand new object which can be used solely for "Segment" reporting.**
>
> **الترجمة الدقيقة لكلام المؤلف:**
> السؤال الذي طُرح عليّ عدة مرات هو: بما أنه يوجد بالفعل كائنان يمكن استخدامهما لإنشاء القوائم المالية (وإن كان ذلك جزئياً)، فلماذا قدمت SAP كائناً جديداً تماماً (أي Segments) لتلبية متطلبات التقارير القطاعية؟
> الإجابة التي وجدتها هي أن معظم عملاء SAP يستخدمون مراكز الربحية ومناطق الأعمال لأغراض أخرى (على سبيل المثال، رأيت عملاء يستخدمون مراكز الربحية كمراكز تكلفة، أو مصانع، أو مناطق مبيعات)، وبالتالي قد يكون من الصعب تحويل هذه الكائنات إلى كيانات لإعداد تقارير القوائم المالية الكاملة. ويكتسب هذا الأمر أهمية خاصة في الحالات التي تمتلك فيها الشركات المئات (أو حتى الآلاف) من مراكز الربحية أو مناطق الأعمال. ولهذا السبب تم تقديم القطاعات (Segments) بحيث يكون لديك كائن جديد تماماً يمكن استخدامه حصرياً لإعداد «التقارير القطاعية».

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - معضلة التفتيت الرقابي (Granularity Dilemma) وعلاقة M:1]**
>
> **التشريح العملي لما ذكره Paul Ovigele حول مئات أو آلاف مراكز الربحية:**
>
> * **حالة واقعية من المشاريع الكبرى:** في شركات التجزئة أو المقاولات أو التصنيع متعدد المصانع، تقوم الإدارة بإنشاء **Profit Center لكل فرع متجر، أو لكل خط إنتاج، أو لكل مشروع كبير** لقياس أداء مدير الفرع أو مدير المشروع داخلياً. النتيجة هي وجود **500 إلى 3,000 Profit Center**!
> * **ماذا يحدث لو فعّلنا Document Splitting مع Zero-Balance على 2,000 Profit Center فقط بدون Segment؟**
>   1. **انفجار حجم القيود المحاسبية (Line Item Explosion):** عندما يتم سداد فاتورة مورد واحدة تشمل توريدات لـ 50 فرعاً (50 Profit Centers)، يقوم محرك Document Splitting بتفكيك سطر البنك وسطر التسوية الصفرية إلى 50 سطراً فرعياً في جدول `ACDOCA`.
>   2. **عدم ملاءمة التفصيل المفرط للتقارير الخارجية:** هيئة سوق المال (SEC / IASB) والمساهمون لا يريدون قراءة قائمة مركز مالي مقسمة إلى 2,000 فرع، بل يريدون رؤية **4 إلى 8 قطاعات استراتيجية كبرى** (مثلاً: قطاع التجزئة، قطاع الجملة، قطاع التجارة الإلكترونية).
>   3. **الحل المعماري الذكي عبر علاقة (Many-to-One `N:1`):**
>      في SAP، كل **Profit Center** يحتوي في بياناته الأساسية (`KE51` - تبويب Basic Data) على حقل واحد اسمه **Segment**. وبذلك يمكن ربط **300 Profit Center** بـ **Segment واحد**!
>      * **للتقارير الإدارية الداخلية (CO/Management):** تحلل الأداء تفصيلياً على مستوى الـ 300 Profit Center.
>      * **للتقارير المالية القانونية الخارجية (External IFRS 8 / SEC Reporting):** تجمع القوائم المالية المتوازنة تلقائياً على مستوى الـ 5 Segments فقط!

### 6. نصيحة المؤلف الاستشارية للمشاريع الجديدة (Greenfield Implementations)

> [!NOTE]
> 🟦 **[كلام الكاتب الأصلي - الفقرة 12 (الأخيرة)]**
>
> **One thing that I caution clients about is that they should not think that Segment reporting can only be satisfied by the use of segments. In fact, if you are carrying out a brand new SAP implementation I recommend that you use profit centers (along with document splitting functionality) for segment reporting. I would leave business areas alone, if you are a new company, since (as mentioned above) the future of this functionality is still uncertain.**
>
> **الترجمة الدقيقة لكلام المؤلف:**
> هناك أمر واحد أحذر العملاء بشأنه، وهو ألا يعتقدوا أن التقارير القطاعية لا يمكن تلبيتها إلا باستخدام كائن القطاعات (Segments). في الواقع، إذا كنت تنفذ تطبيقاً جديداً تماماً لنظام SAP (Brand New Implementation)، فإنني أوصي باستخدام مراكز الربحية (Profit Centers) — جنباً إلى جنب مع خاصية تقسيم المستندات (Document Splitting) — لإعداد التقارير القطاعية. وأنصح بترك مناطق الأعمال (Business Areas) جانباً إذا كنت شركة جديدة، نظراً لأن مستقبل هذه الوظيفة (كما ذُكر أعلاه) لا يزال غير مؤكد.

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - متى نكتفي بـ Profit Center ومتى نجمع بين Profit Center و Segment؟]**
>
> **تقييم توصية المؤلف في ضوء معمارية SAP S/4HANA الحديثة:**
>
> توصية Paul Ovigele دقيقة جداً، ويمكن تفصيلها استشارياً وفق سيناريوهين:
> * **السيناريو الأول (عدد مراكز الربحية محدود ومطابق للقطاعات الخارجية):**
>   إذا كانت الشركة في مشروع جديد (**Greenfield Implementation**) تصمم هيكلها بحيث يكون لديها مثلاً 6 مراكز ربحية تمثل هي نفسها القطاعات الستة الخارجية، أو تستخدم **Profit Center Hierarchy (`KCH1`)** لتجميع مراكز الربحية، فيمكنها الاعتماد على `Profit Center` مباشرة مع `Document Splitting`.
> * **السيناريو الثاني (التصميم القياسي الموصى به في S/4HANA Best Practices):**
>   حتى في المشاريع الجديدة، تنصح **SAP Best Practices** بتفعيل كلٍّ من `Profit Center` و `Segment` معاً كخصائص تقسيم (**Splitting Characteristics**) في شاشة الإعدادات، لأن تفعيل `Segment` منذ اليوم الأول في `KE51` لا يكلّف أي جهد إضافي من المستخدم النهائي (لأنه يُشتق أوتوماتيكياً من الـ Profit Center بنسبة 100%)، وفي الوقت نفسه يمنح الشركة **مرونة مستقبلية كاملة** إذا توسعت مراكز الربحية لاحقاً إلى مئات المراكز دون المساس بثبات القطاعات الخارجية.

## القسم الثالث: مصفوفة المقارنة الشاملة بين الكائنات التنظيمية الأربعة في SAP

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - مقارنة معمارية وتنظيمية شاملة]**
> توضح المصفوفة التالية الفروقات الجوهرية بين الكائنات الأربعة التي ناقشها المؤلف من حيث الغرض، الجداول التقنية، والاشتقاق:

| وجه المقارنة | Company Code (`BUKRS`) | Business Area (`GSBER`) | Profit Center (`PRCTR`) | Segment (`SEGMENT`) |
| :--- | :--- | :--- | :--- | :--- |
| **التعريف الجوهري** | وحدة محاسبية قانونية مستقلة تمثل شركة مسجلة قانونياً | تقسيم تنظيمي أفقي للأنشطة عبر أكواد الشركات | وحدة رقابية إدارية داخلية لقياس الربحية والمسؤولية | قطاع أعمال أو منطقة جغرافية لإعداد القوائم المالية الخارجية |
| **الجمهور المستهدف** | الجهات الضريبية، البنوك، المسجل التجاري، المراجع القانوني | تقارير خارجية/داخلية (في الأنظمة الكلاسيكية القديمة) | الإدارة العليا، مديرو الفروع وخطوط الإنتاج (Internal Control) | هيئات سوق المال (SEC)، المساهمون، معايير IFRS 8 / ASC 280 |
| **مستوى التفصيل (Granularity)** | منخفض (حسب عدد السجلات القانونية للمجموعة) | متوسط إلى مرتفع | مرتفع جداً (قد يصل لمئات أو آلاف المراكز) | منخفض ومركز (عادةً من 3 إلى 10 قطاعات استراتيجية) |
| **طريقة الاشتقاق القياسية (Derivation)** | يُحدد في ترويسة المستند (Document Header) | يُشتق من Plant/Division أو يُدخل يدوياً | يُشتق من Cost Center، Material، Internal Order، WBS، أو Sales Order | يُشتق **تلقائياً** من سجل البيانات الأساسية للـ Profit Center (`CEPC-SEGMENT`) |
| **الجدول الرئيسي للبيانات الأساسية** | `T001` | `TGSB` | `CEPC` / `CEPCT` | `FAGL_SEGM` / `FAGL_SEGMT` |
| **الموقف في SAP S/4HANA** | أساسي وإلزامي في كل قيد | متقادم (Legacy/Deprecated) لا يُنصح به للمشاريع الجديدة | أساسي ومحوري داخل `ACDOCA` | أساسي ومحوري للتقارير القطاعية داخل `ACDOCA` |

## القسم الرابع: الآلية التقنية لعمل الـ Segment ومنطق SAP (SAP Technical Logic)

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - كيف يعمل الـ Segment تقنياً داخل النظام؟]**
>
> **1. سلسلة الاشتقاق التلقائي (The Golden Derivation Chain):**
> في نظام SAP، **لا يقوم المحاسب أو مدخل الفاتورة باختيار الـ Segment يدوياً** في الحالات القياسية؛ بل يعمل النظام وفق سلسلة وراثة محكمة:
>
> * **المواد والأصناف (Materials):** `Material Master (MM01/MM02)` في المصنع (`Plant`) يحتوي على `Profit Center` ⬅️ يشتق منه الـ `Segment`.
> * **مراكز التكلفة (Cost Centers):** `Cost Center (KS01)` يحتوي على `Profit Center` ⬅️ يشتق منه الـ `Segment`.
> * **المشاريع والأوامر الداخلية (WBS & Internal Orders):** `WBS Element (CJ20N)` أو `Internal Order (KO01)` يحتوي على `Profit Center` ⬅️ يشتق منه الـ `Segment`.
> * **أوامر المبيعات (Sales Orders):** `Sales Order Item (VA01)` يرث الـ `Profit Center` من الصنف/المصنع ⬅️ يشتق منه الـ `Segment`.
>
> **2. محرك تقسيم المستندات (Document Splitting Engine) والتسوية الصفرية:**
> المشكلة الكبرى في المحاسبة المالية التقليدية هي أن **المصروفات والإيرادات** تعرف مركز ربحيتها وقطاعها، بينما **بنود الميزانية العمومية** (مثل الموردين `Vendor Recon Account`، العملاء `Customer Recon Account`، البنوك `Bank Account`، وضريبة القيمة المضافة `VAT`) يتم ترحيلها بإجمالي الفاتورة بدون قطاع!
>
> هنا يتدخل **Document Splitting** عبر ثلاث مراحل متتالية:
> 1. **التقسيم الساكن (Passive Splitting):** يعمل عند **السداد أو التحصيل** (`F-53`, `F-28`, `F110`). ينظر النظام إلى الفاتورة الأصلية التي يتم سدادها، ويورث نسب الـ `Segment` والـ `Profit Center` منها إلى قيد البنك والخصم النقدي بنفس النسب تماماً.
> 2. **التقسيم النشط القائم على القواعد (Active / Rule-Based Splitting):** يعمل عند **إثبات الفاتورة** (`FB60`, `MIRO`, `FB70`, `VF01`). ينظر النظام إلى بنود المصروفات أو الإيرادات (`Item Categories 20000 / 30000`) ويقوم بتقسيم بند المورد أو العميل والضرائب (`Item Categories 03000 / 02000 / 05100`) بنفس النسب المالية.
> 3. **التوازن الصفري (Zero-Balance Clearing Line Items):** عندما يتم إجراء تحويل مالي أو تسوية بين قطاعين مختلفين (مثلاً نقل أصل أو مصروف مشترك بين `SEG_A` و `SEG_B`)، يقوم النظام تلقائياً بتوليد أسطر تسوية على حساب وسيط (**Zero-Balance Clearing Account**) بحيث يخرج كل Segment وميزانيته متوازنة (`Debit = Credit = 0`) في نفس اللحظة!

> [!IMPORTANT]
> 🟪 **[قاعدة ذهبية في SAP حول تعديل الـ Segment]**
> بمجرد إدخال الـ `Segment` داخل شاشة تعريف الـ `Profit Center` (`KE51`) وحفظه وترحيل قيود عليه، يصبح حقل الـ Segment في الـ Profit Center **غير قابل للتعديل المباشر** إلا عبر إجراءات إعادة التنظيم الرسمية (**Segment Reorganization / Profit Center Reorganization**) لضمان عدم تشوه أرصدة الميزانية التاريخية!

### مثال رقمي تطبيقي لقيد مقسم عبر محرك Document Splitting

لنفترض ورود فاتورة مشتريات خدمات بقيمة **1,000 دولار** (بدون ضرائب للتبسيط) من مورد واحد، تخص قسمين في الشركة:
* **600 دولار** تخص مركز تكلفة يتبع `Profit Center PC01` المربوط بـ `Segment SEG_RETAIL`.
* **400 دولار** تخص مركز تكلفة يتبع `Profit Center PC02` المربوط بـ `Segment SEG_WHOLESALE`.

| عرض القيد (View) | السطر | الحساب | المدين (Dr) | الدائن (Cr) | Profit Center | Segment |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **1. شاشة الإدخال (Entry View - `BSEG`)** | 001 | حساب المورد (Vendor) | 0 | 1,000 | *(فارغ)* | *(فارغ)* |
| **1. شاشة الإدخال (Entry View - `BSEG`)** | 002 | مصروف خدمات 1 | 600 | 0 | `PC01` | `SEG_RETAIL` |
| **1. شاشة الإدخال (Entry View - `BSEG`)** | 003 | مصروف خدمات 2 | 400 | 0 | `PC02` | `SEG_WHOLESALE` |
| **2. شاشة الأستاذ العام (G/L View - `ACDOCA`)** | 001-A | حساب المورد (Vendor) | 0 | **600** | `PC01` | `SEG_RETAIL` |
| **2. شاشة الأستاذ العام (G/L View - `ACDOCA`)** | 001-B | حساب المورد (Vendor) | 0 | **400** | `PC02` | `SEG_WHOLESALE` |
| **2. شاشة الأستاذ العام (G/L View - `ACDOCA`)** | 002 | مصروف خدمات 1 | **600** | 0 | `PC01` | `SEG_RETAIL` |
| **2. شاشة الأستاذ العام (G/L View - `ACDOCA`)** | 003 | مصروف خدمات 2 | **400** | 0 | `PC02` | `SEG_WHOLESALE` |

## القسم الخامس: أثر الـ Segment على جميع موديولات SAP (Cross-Module Impact Analysis)

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - كيف يتأثر كل موديول في SAP بتفعيل الـ Segments؟]**
> تفعيل الـ `Segment` وتحديده كحقل إجباري ومتوازن (`Required & Zero-Balance Field`) في الأستاذ العام لا يقتصر أثره على موديول FI، بل يمتد عبر كافة العمليات اللوجستية والرأسمالية والبشرية في النظام:

| الموديول (SAP Module) | نقطة التكامل الأساسية | كيف ينتقل الـ Segment؟ | التحديات والضوابط التشغيلية (Key Controls & Challenges) |
| :--- | :--- | :--- | :--- |
| **1. المحاسبة المالية (FI - G/L, AP, AR, Bank)** | قيود اليومية، فواتير الموردين والعملاء، السداد الآلي (`F110`)، فروق العملة (`FAGL_FCV`) | عبر تقسيم المستندات (`Active & Passive Splitting`) من الحسابات المقابلة | • يجب تصنيف كافة حسابات الأستاذ العام (`GSP_LZ2`) إلى فئات بنود صحيحة (`Item Categories`).<br>• إعادة تقييم العملات الأجنبية في آخر الشهر ترحّل فروق التقييم تلقائياً على نفس الـ Segment الخاص بالفاتورة الأصلية. |
| **2. المحاسبة الإدارية والتكاليف (CO - OM, PCA, PA)** | مراكز التكلفة (`KS01`)، الأوامر الداخلية (`KO01`)، توزيعات التكاليف (`KSV5`/`KSU5`)، تحليل الربحية (`CO-PA`) | كل كائن تكلفة يحتوي على `Profit Center` يشتق منه الـ `Segment` لحظياً | • عند إجراء توزيعات نهاية الشهر (`Assessment / Distribution`) بين مراكز تكلفة تتبع قطاعات مختلفة، يقوم التكامل اللحظي بين CO و FI بتوليد قيد تسوية صفري بين القطاعات.<br>• يظهر الـ Segment كبُعد تحليلي جاهز في تقارير الربحية `Margin Analysis`. |
| **3. إدارة المواد والمشتريات (MM - Materials Management)** | استلام البضائع (`MIGO`)، مراقبة الفواتير (`MIRO`)، جرد المخزون (`MI07`) | من شاشة بيانات الصنف في المصنع (`Material Master -> Plant Data / Storage` أو `Sales: General/Plant` -> `Profit Center` -> `Segment`) | • **نقطة حرجة:** إذا تم ترك حقل الـ `Profit Center` فارغاً في كارت الصنف (`MM01/MM02`)، سيفشل استلام البضاعة (`MIGO`) برسالة خطأ `Balancing field "Segment" in line item 001 not filled`!<br>• حساب وسيط استلام البضاعة `GR/IR` يورث الـ Segment من بند المخزون أو مركز التكلفة. |
| **4. المبيعات والتوزيع (SD - Sales & Distribution)** | أوامر البيع (`VA01`)، تسليم البضاعة (`VL01N`)، فواتير المبيعات (`VF01`) | من بند أمر البيع (`Sales Order Item`) الذي يشتق الـ `Profit Center` من كارت الصنف أو من قواعد الاستبدال (`OKB9` / `VKOA`) | • عند صرف البضاعة للعميل (`PGI - VL01N`)، يأخذ قيد تكلفة البضاعة المباعة (`COGS`) والمخزون الـ Segment من الصنف.<br>• عند إصدار الفاتورة (`VF01`)، يتقسم مدين العميل (`Customer Line`) وحساب ضريبة المبيعات تلقائياً حسب قطاعات الأصناف المباعة في الفاتورة. |
| **5. تخطيط ومراقبة الإنتاج (PP & CO-PC)** | أوامر الإنتاج (`CO01`)، استهلاك الخامات، تسوية فروق الإنتاج (`KO88`) | يرث أمر الإنتاج (`Production Order`) مركز الربحية والـ Segment من الصنف التام الصنع (`Header Material`) | • إذا تم سحب مادة خام تتبع `Segment A` لتصنيع منتج تام يتبع `Segment B`، يتدخل حساب التسوية الصفرية (`Zero-Balance Clearing`) لموازنة المخزون بين القطاعين لحظة حركة الصرف `261`. |
| **6. الأصول الثابتة (FI-AA - Asset Accounting)** | شراء الأصل (`F-90`)، الإهلاك الشهري (`AFAB`)، نقل الأصول (`ABUMN`)، الاستبعاد (`F-92`) | يرتبط كارت الأصل الثابت (`AS01`) بـ `Cost Center` أو `Internal Order`/`WBS`، ومنه يشتق `Profit Center` و `Segment` | • في **SAP S/4HANA (New Asset Accounting)**، يمكن تفعيل حقل الـ `Segment` والـ `Profit Center` مباشرة في بيانات الأصل الثابت المرتبطة بالوقت (`Time-Dependent Data - Table ANLZ`) وتفعيل خيار **Account Assignment Objects for Balance Sheet** (`ACSET`)، بحيث تترحل قيمة الأصل ومجمع الإهلاك ومصروف الإهلاك جميعها على نفس الـ Segment بدقة تامة. |
| **7. إدارة المشروعات (PS - Project System)** | هيكل تجزئة العمل (`WBS Elements - CJ20N`)، الشبكات (`Networks`)، تسوية المشاريع (`CJ88`) | كل `WBS Element` يحتوي إلزامياً على `Profit Center` يشتق منه الـ `Segment` | • جميع التكاليف المتجمعة على المشروع (أعمال تحت التنفيذ `WIP / AuC`) تحمل الـ Segment الخاص بالـ WBS Element حتى لحظة الرأسمالية النهائية للأصل. |
| **8. الموارد البشرية والرواتب (HCM / SuccessFactors Payroll)** | ترحيل مسير الرواتب الشهري إلى الحسابات (`PCP0`) | من التعيين التنظيمي للموظف (`Infotype 0001` أو `0027 Cost Distribution`) -> `Cost Center` -> `Profit Center` -> `Segment` | • مصروفات الأجور والبدلات تذهب لقطاعات الموظفين، بينما حسابات الاستحقاقات الدائنة (`Payroll Liabilities` والتأمينات وضريبة كسب العمل) يتم تقسيمها تلقائياً عبر Document Splitting أو عبر حسابات وسيطة موزعة بالقطاع. |

## القسم السادس: خارطة طريق الإعدادات التقنية في SAP (Configuration Blueprint & T-Codes)

> [!TIP]
> 🟩 **[إثراء وتحليل معمق - الدليل التطبيقي للاستشاريين (IMG Paths & Transactions)]**
> لتنفيذ منظومة التقارير القطاعية (Segment Reporting) بشكل سليم في SAP ECC (New G/L) أو SAP S/4HANA، يمر الاستشاري بالخطوات الهندسية التالية بالترتيب:

| الخطوة | اسم الإعداد التقني | مسار SPRO / الكود المختصر (T-Code) | الجدول التقني | الغرض والضوابط الاستشارية |
| :--- | :--- | :--- | :--- | :--- |
| **1** | **تعريف القطاعات (Define Segments)** | `SPRO -> Enterprise Structure -> Definition -> Financial Accounting -> Define Segment` | `FAGL_SEGM` | إنشاء أكواد القطاعات العليا (مثلاً: `SEG_01`, `SEG_02`) بأوصاف واضحة تعكس خطوط الأعمال الخارجية. |
| **2** | **ربط القطاع بمركز الربحية** | `KE51` / `KE52` (تطبيق Fiori: *Manage Profit Centers*) | `CEPC` | إدخال الـ `Segment` في تبويب Basic Data لكل Profit Center. (العلاقة `Many Profit Centers : 1 Segment`). |
| **3** | **تفعيل سيناريو الـ Segment في الليدجر** | `SPRO -> Financial Accounting (New) -> Financial Accounting Global Settings (New) -> Ledgers -> Ledger -> Assign Scenarios and Customer Fields to Ledgers` | `FAGL_LEDGER_SCEN` | في ECC New G/L يتم ربط سيناريو `FIN_SEGM` (Segmentation) و `FIN_PCA` بالليدجر الرئيسي `0L`. (في S/4HANA مدمج تلقائياً في `ACDOCA`). |
| **4** | **تصنيف حسابات الأستاذ العام للتقسيم** | `GSP_LZ2` (*Classify G/L Accounts for Document Splitting*) | `T8G17` | ربط فترات حسابات شجرة الحسابات بفئات البنود (`Item Categories` مثل `01000` للميزانية، `04000` للنقدية، `20000` للمصروف، `30000` للإيراد). |
| **5** | **تصنيف أنواع المستندات للتقسيم** | `GSP_VZ3` (*Classify Document Types for Document Splitting*) | `T8G12` | ربط كل نوع مستند (`SA`, `KR`, `DR`, `ZP`, `WA`) بمعاملة تجارية (`Business Transaction` و `Variant`). |
| **6** | **تعريف حساب التسوية الصفرية** | `GSP_KD1` (*Define Zero-Balance Clearing Account*) | `T8G30A` | تحديد حساب أستاذ عام وسيط يوازن القيود التي تعبر أكثر من Segment أو Profit Center داخل نفس المستند. |
| **7** | **تعريف خصائص التقسيم للأستاذ العام** | `GSP_KD2` (*Define Document Splitting Characteristics for General Ledger Accounting*) | `FAGL_SPLIT_FIELD` | وضع علامة صح على **Zero Balance** و **Mandatory Field** أمام حقل `SEGMENT` وحقل `PRCTR`. |
| **8** | **تفعيل تقسيم المستندات** | `FAGL_ACTIVATION` (*Activate Document Splitting*) | `FAGL_SPLIT_ACT` | تفعيل التقسيم على مستوى الـ Client مع إمكانية استثناء Company Codes معينة عند الحاجة، وتحديد `Constant` احتياطي إن لزم. |
| **9** | **تكامل الأصول الثابتة مع الـ Segment** | `ACSET` (*Specify Account Assignment Types for Account Assignment Objects*) | `T093_ACCOBJ` | تفعيل `SEGMENT` و `PRCTR` لحركتي الميزانية (`APC`) والإهلاك (`Depreciation Run`) في موديول الأصول. |

## القسم السابع: الأخطاء الشائعة وأفضل الممارسات الاستشارية (Best Practices & Pitfalls)

> [!IMPORTANT]
> 🟪 **[إثراء وتحليل معمق - خلاصة الخبرات العملية وأشهر الأخطاء في مشاريع SAP]**
>
> **1. أشهر الأخطاء القاتلة التي يقع فيها العملاء (Common Pitfalls):**
> * **الخطأ الأول (العلاقة 1:1 غير المبررة):** إنشاء Segment منفصل لكل Profit Center (مثلاً 500 Profit Center مقابل 500 Segment). هذا يلغي تماماً الفائدة المعمارية للـ Segment التي شرحها Paul Ovigele ويزيد تعقيد التقارير الخارجية بلا داعٍ.
> * **الخطأ الثاني (استخدام Dummy Segment كحل دائم):** إنشاء قطاع وهمي (`DUMMY_SEG`) وتفعيله كـ Default Constant في Document Splitting للتخلص من رسائل الخطأ أثناء الترحيل! هذا يؤدي إلى تراكم أرصدة ضخمة غير مصنفة في قطاع وهمي يفقد القوائم المالية مصداقيتها أمام المراجع الخارجي.
> * **الخطأ الثالث (إغفال الحسابات الوسيطة والبنكية):** نسيان تصنيف حسابات التسوية البنكية (`Bank Sub-accounts`) أو حسابات `GR/IR` في شاشة `GSP_LZ2`، مما يعطل الدورة المستندية للسداد أو الفوترة.
>
> **2. مصفوفة اتخاذ القرار النهائي للمشاريع (Decision Matrix):**
> * **إذا كان المشروع Greenfield (تطبيق جديد بالكامل على S/4HANA):**
>   * **تجاهل تماماً `Business Area`** (لا تقم بتفعيلها).
>   * **صمّم هيكل `Profit Centers`** ليعكس وحدات المساءلة الإدارية الداخلية (المصانع، الفروع، خطوط المنتجات).
>   * **صمّم هيكل `Segments`** ليعكس قطاعات الإفصاح المالي الخارجي العليا وفق **IFRS 8 / ASC 280**، واربط كل مجموعة مراكز ربحية بالقطاع الخاص بها.
>   * **فعّل `Document Splitting` مع `Zero-Balance`** لكلا الحقلين (`PRCTR` و `SEGMENT`).
> * **إذا كان المشروع Brownfield (تحويل نظام قائم يستخدم Profit Centers بكثافة لأغراض أخرى):**
>   * هنا تتجلى العبقرية التي ذكرها Paul Ovigele؛ إذ يمكنك الإبقاء على آلاف مراكز الربحية القائمة كما هي دون هدم هيكل التقارير الداخلية، وبناء طبقة نظيفة من الـ **Segments** فوقها لتلبية متطلبات المراجع الخارجي وهيئات سوق المال.
