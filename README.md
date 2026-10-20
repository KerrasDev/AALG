# وثيقة التصميم العلمي والهندسي لنظام:
## فضاء الرسم البياني المعجمي المائي العربي
### Aquatic Arabic Lexical Graph (AALG) — Architecture & Specification Document

---

## مقدمة الفريق والتأطير المنهجي

صُممت هذه الوثيقة بواسطة فريق عمل متكامل يضم اختصاصات: اللسانيات العربية وفقه اللغة، اللسانيات المقارنة والساميات، هندسة الشبكات المعرفية والرسوم البيانية، المعالجة الحاسوبية للغة العربية (NLP)، النماذج اللغوية والاستدلال الآلي، الإحصاء وتصميم التجارب، وهندسة النظم البرمجية.

الهدف الأساسي للنظام ليس الانتصار المسبق لفرضية «الأصل المائي للغة العربية» ولا إسقاطها اعتباطياً، بل تأسيس **منصة تدقيق وتحقيق حاسوبية صارمة ومحكمة علمياً**. يستكشف النظام المسارات الدلالية والصوتية والاشتقاقية المحتملة بين مفهوم «الماء» ومعجم اللغة العربية، ويخضع كل مسار لاختبارات تفنيد (*Falsification*) وضوابط صوتية ومقارنات تاريخية سامية تفرز بدقة متناهية بين:
1. **الاشتقاق التاريخي الموثق بشواهد ونقوش وقوانين صوتية منتظمة.**
2. **التوسع الدلالي والمجازي في سياق البيئة المعجمية العربية.**
3. **التشابه العرضي والاشتقاق الشعبي الزائف (*Folk Etymology*).**

---

```
                       +---------------------------------------+
                       |       المدخلات: معجم + نقوش + نصوص    |
                       +---------------------------------------+
                                           |
                                           v
+-----------------------------------------------------------------------------------+
|                           طبقات الرسم البياني والمعرفة                             |
|                                                                                   |
|  [L1: الطبقة الدلالية]   [L2: الطبقة الصرفية]   [L3: الطبقة الصوتية]   [L4: التاريخية السامية] |
+-----------------------------------------------------------------------------------+
                                           |
                                           v
+-----------------------------------------------------------------------------------+
|                        محرك توليد الفرضيات والمسارات                              |
|  - مقيد بـ Max Hops = 4        - تكلفة تحولات صوتية        - منع التوليد العشوائي  |
+-----------------------------------------------------------------------------------+
                                           |
                                           v
+-----------------------------------------------------------------------------------+
|                        طبقة التفنيد والتحقق الصارم                                |
|  - فحص القوانين الصوتية       - اختبار النماذج المقابلة (حجر/نار)  - استدعاء الأدلة المعاكسة |
+-----------------------------------------------------------------------------------+
                                           |
                                           v
+-----------------------------------------------------------------------------------+
|                   النموذج الرياضي التكاملي والتقييم البايزي                        |
|             Score(P) = Evidence(P) - Complexity(P) - Contradictions(P)             |
+-----------------------------------------------------------------------------------+
                                           |
               +---------------------------+---------------------------+
               |                                                       |
               v                                                       v
+-----------------------------+                         +-----------------------------+
|    مسارات مقبولة ومدعومة     |                         |     مسارات مرفوضة وزائفة     |
| (اشتقاق مثبت / تجوز دلالي)  |                         |  (تلفيق صوتي / مصادفة محضة) |
+-----------------------------+                         +-----------------------------+
```

---

## 1. بنية الطبقات الاثنتي عشرة للنظام (System Layered Architecture)

يتكون نظام `AALG` من 12 طبقة معمارية مفصولة المسؤوليات (*Separation of Concerns*):

```
+------------------------------------------------------------------------------+
| 12. طبقة التوثيق وإعادة الإنتاج (Provenance, Git-Data, Audit Logs)             |
+------------------------------------------------------------------------------+
| 11. طبقة واجهة الاستكشاف والتصور (Visual Exploration, Graph Explorer)         |
+------------------------------------------------------------------------------+
| 10. طبقة التقييم الإحصائي والمعايرة (Statistical Calibration, Null Hypothesis) |
+------------------------------------------------------------------------------+
| 9.  طبقة المقارنة والتفنيد (Falsification Layer, Competing Explanations)     |
+------------------------------------------------------------------------------+
| 8.  طبقة التحقق من الأدلة والشواهد (Evidence Verification Engine)             |
+------------------------------------------------------------------------------+
| 7.  طبقة البحث عن المسارات (Constrained Path Finding Engine)                 |
+------------------------------------------------------------------------------+
| 6.  طبقة توليد الفرضيات المقيدة (Constrained Hypothesis Generation)          |
+------------------------------------------------------------------------------+
| 5.  طبقة الشبكة المعرفية الهجينة (Multi-Relational Heterogeneous Graph)      |
+------------------------------------------------------------------------------+
| 4.  طبقة القوانين الصوتية والتاريخية المقارنة (Phonetic & Comparative Semitic) |
+------------------------------------------------------------------------------+
| 3.  طبقة الجذور والصيغ الصرفية (Roots & Morphological Patterns)               |
+------------------------------------------------------------------------------+
| 2.  طبقة المفاهيم والأنساق الدلالية (Ontological Concepts & Synsets)          |
+------------------------------------------------------------------------------+
| 1.  طبقة البيانات اللغوية الموثقة (Linguistic Corpus, Inscriptions, Lexica)  |
+------------------------------------------------------------------------------+
```

### توصيف وتفاعل الطبقات:

1. **طبقة البيانات اللغوية (Corpus & Lexicon Data Layer):**
   - *الوظيفة:* استيعاب وضبط وتخزين المادة المعجمية الخام من أمهات المعاجم (العين، مقاييس اللغة، المحكم، لسان العرب، تاج العروس)، والنقوش العربية القديمة والسامية (المسند، النبطية، السريانية، الأوغاريتية، الأكدية، العبرية).
   - *المدخلات:* نصوص ومعاجم ونقوش رقمية محققة.
   - *المخرجات:* نصوص موحدة مشكولة ومفهرسة بمعرفات استشهاد قياسية.
2. **طبقة المفاهيم والأنساق الدلالية (Semantic Concept Layer):**
   - *الوظيفة:* بناء شبكة أنطولوجية دلالية تفصل بين المعنى التجريدي واللفظ.
   - *المدخلات:* معاني الألفاظ المعجمية.
   - *المخرجات:* عقد مفاهيمية متصلة بروابط تصنيفية (*Is-A, Part-Of, State-Of*).
3. **طبقة الجذور والصيغ الصرفية (Morphological Layer):**
   - *الوظيفة:* التحليل المورفولوجي الدقيق للألفاظ، ورد المشتقات إلى جذورها الفعلية (ثلاثية، رباعية، ثنائية الأصل المفترض)، وتجريد الزوائد والأوزان الصرفية.
   - *المخرجات:* فصل تام بين الوزن الصرفي والجذر المعجمي.
4. **طبقة القوانين الصوتية والتاريخية المقارنة (Phonetic & Comparative Layer):**
   - *الوظيفة:* ترميز القوانين الصوتية المنتظمة للغات السامية والتحولات الصوتية داخل العربية (مثل قوانين غريم-فيرنر في الساميات، والهمس، والجهر، والإبدال المعجمي المقيس).
   - *المخرجات:* مصفوفة كلفة التحول الصوتي والجواز اللساني التاريخي.
5. **طبقة الشبكة المعرفية الهجينة (Multi-Relational Graph Layer):**
   - *الوظيفة:* تمثيل كافة الكيانات والعلاقات في شبكة رياضية متعددة العلاقات والأنواع `G = (V, E, T, A)`.
   - *المخرجات:* نموذج بياني قابل للاستعلام السريع والتنقل الطوبولوجي.
6. **طبقة توليد الفرضيات المقيدة (Hypothesis Generation Layer):**
   - *الوظيفة:* اقتراح روابط افتراضية محتملة لسد الفجوات بين الجذور غير المفسرة ومفهوم الماء، استناداً إلى تشابهات دلالية أو صوتية مقيدة.
   - *المخرجات:* روابط مؤقتة موسومة صراحة بأنها `HYPOTHETICAL`.
7. **طبقة البحث عن المسارات (Path Search Engine):**
   - *الوظيفة:* البحث المقيد عن سلاسل الربط بين عقدة الماء المستهدفة والجذر المراد فحصه، وفق خوارزميات محددة العمق والكلفة.
   - *المخرجات:* مسارات مرشحة مقيدة بحد أقصى للمسافة وتكلفة الانتقال.
8. **طبقة التحقق من الأدلة والشواهد (Evidence Verification Engine):**
   - *الوظيفة:* ربط كل حافة في المسار بشاهد نصي أو معجمي مؤرخ، وحساب درجة موثوقية السند التاريخي لكل خطوة.
   - *المخرجات:* مصفوفة الأوزان الإثباتية المستندة للمصادر.
9. **طبقة المقارنة والتفنيد (Falsification & Competing Layer):**
   - *الوظيفة:* **حجر الزاوية المانع للتحيز**؛ تولد نماذج منافسة (تفسير أصل الكلمة من بيئة الحجر، النار، النبات)، وتبحث عن شواهد مضادة وتناقضات صريحة.
   - *المخرجات:* تقرير التناقضات واحتساب جزاء الشذوذ (*Contradiction Penalty*).
10. **طبقة التقييم الإحصائي والمعايرة (Statistical & Scoring Layer):**
    - *الوظيفة:* تطبيق المعادلة الرياضية التقييمية ومقاييس بايز لحساب درجة الدعم، وتطبيق اختبارات الفرضية الصفرية (*Monte Carlo / Permutation Tests*).
    - *المخرجات:* درجات ثقة قطعية، وترجيحية، ومعامل دلالة إحصائية ($p\text{-value}$).
11. **طبقة واجهة الاستكشاف والتصور (Visual Exploration Layer):**
    - *الوظيفة:* بيئة بصرية تفاعلية تمكّن الباحث من فحص المسارات، وتلوين الحواف وفق درجة الإثبات ونوع الرابطة، والاطلاع على الشواهد والأدلة المقابلة.
    - *المخرجات:* واجهة غرافيكية ورسوم بيانية ديناميكية.
12. **طبقة التوثيق وإعادة الإنتاج (Provenance & Audit Layer):**
    - *الوظيفة:* حفظ كل عملية استدلال، وكل تغيير للأوزان، وكل استعلام مع شجرة المصادر غير القابلة للتغيير (*Immutable Audit Trail*).
    - *المخرجات:* تقارير مراجعة مؤرخة ببصمات تشفيرية (SHA-256).

---

## 2. المخرجات الهندسية والعلمية التفصيلية

### المخرج A: وثيقة التصميم العلمي (Scientific Specification)

#### 1. صياغة الفرضية المركزية وحدودها
* **نص الفرضية البحثية ($H_1$):** «يمثل مفهوم الماء ومشتقاته ومظاهره البيئية والفيزيائية رافداً تفسيرياً مركزياً لنشأة وتطور نسبة ذات دلالة إحصائية من الجذور المعجمية العربية، تتجاوز النسبة المتوقعة عشوائياً في المعاجم السامية».
* **الفرضية الصفرية المقابلة ($H_0$):** «توزيع العلاقات الدلالية والصوتية بين الجذور العربية ومفهوم الماء لا يختلف عن التوزيع الإحصائي العشوائي لأي مفهوم طبيعي مركزي آخر (مثل: الأرض/الحجر، النار/الحرارة، الريح/الحركة)، وأي علاقات إضافية مفترضة هي نتاج الاشتقاق الشعبي والتحولات الصوتية غير المقيدة».
* **الحدود اللسانية الصارمة:**
  - لا يُقبل أي ادعاء بأن *«كل الجذور بلا استثناء تعود إلى الماء»*؛ إذ يُعد هذا الطرح لاغياً علمياً لمخالفته المبدأ البوبري في قابلية التكذيب (*Falsifiability*).
  - الفصل المطلق بين **النشوء الأنطولوجي الحيوي** (مثل قوله تعالى: ﴿وَجَعَلْنَا مِنَ الْمَاءِ كُلَّ شَيْءٍ حَيٍّ﴾) و**التطور اللساني التاريخي** الخاضع لقوانين علم اللغات المقارن والاصطلاح البشري.

#### 2. الكيانات اللغوية الستة والتمييز الحاسم بينها
يُعرّف النظام ستة كيانات متباينة نمطياً:
1. **اللفظ (Surface Form / Lemma - $u$):** الصيغة المنطوقة أو المكتوبة المحددة (مثال: «مَاءٌ»، «مَوْهَةٌ»، «اسْتَمْطَرَ»).
2. **الجذر (Root - $r$):** الوحدة المعجمية التجريدية، سواء كانت ثلاثية قياسية (مثل: $\sqrt{\text{م-و-ه}}$)، أو ثنائية مفترضة تاريخياً، أو غير ثلاثية.
3. **الصيغة الصرفية (Morphological Pattern - $m$):** الوزن الصرفي وبنية الزوائد وعلاقتها بالدلالة (فَعَلَ، افْتَعَلَ، فُعَال).
4. **المعنى المعجمي (Lexical Sense - $s$):** المعنى الاصطلاحي الموثق داخل سياق أو معجم محدد، وله معرّف مستقل لكل مدخل تجنباً للمشتركات اللفظية.
5. **المفهوم الدلالي التجريدي (Ontological Concept - $c$):** المفهوم الذهني الخالص المنفصل عن الألفاظ (مثل: مفهوم `LIQUIDITY`، `STAGNANT_WATER`، `FLOW`).
6. **الشاهد التاريخي (Attestation / Historical Evidence - $e$):** النص، أو بيت الشعر الجاهلي الموثق، أو النقش الأثري (سبئي، نبطي، أكدي)، مع توثيق المصدر والتاريخ التقريبي ومستوى التوثيق.

---

### المخرج B: مخطط الشبكة وقواعد الانتقال (Graph Metamodel & Schema)

تُعرّف الشبكة رياضياً بأنها رسم بياني هجين غير متجانس، موجه وموزون ومتعدد العلاقات:
$$\mathcal{G} = (\mathcal{V}, \mathcal{E}, \mathcal{T}_v, \mathcal{T}_e, \mathcal{A})$$

```
  +-------------------+       INSTANTIATES        +-------------------+
  |   Surface Form    | ------------------------> |   Morph Pattern   |
  +-------------------+                           +-------------------+
      |           |                                         |
      | EXPRESSES | ROOT_OF                                 | APPLIED_TO
      v           v                                         v
+-----------------------+     ABSTRACTED_TO       +-------------------+
|     Lexical Sense     |                         |       Root        |
+-----------------------+                         +-------------------+
      |           |                                         |
      | MAPS_TO   | BACKED_BY                               | COGNATE_TO
      v           v                                         v
+-------------+ +-------------+                   +-------------------+
|   Concept   | | Historical  |                   | Proto-Semitic /   |
| (Water/...) | | Attestation |                   | Historical Root   |
+-------------+ +-------------+                   +-------------------+
```

#### أنواع العقد ($\mathcal{T}_v$):
* `V_LEMMA`: لفظ محدد بهيئته الصوتية والكتابية.
* `V_ROOT`: جذر مجرد معجمي أو مقارن.
* `V_SENSE`: معنى معجمي مقيد بسياق.
* `V_CONCEPT`: مفهوم أنطولوجي مجرد.
* `V_PATTERN`: بنية ووزن صرفي.
* `V_ATTESTATION`: نص أو نقش أثري موثق.
* `V_RULE`: قانون صوتي أو تحول تاريخي معتمد.

#### أنواع الحواف والعلاقات ($\mathcal{T}_e$):

##### الطبقة 1: العلاقات الدلالية (Semantic Edges)
* `E_DIR_WATER_SENSE`: دلالة مائية صريحة ومباشرة (مثال: سكب $\rightarrow$ صب الماء).
* `E_AQUATIC_ENV`: عنصر من عناصر البيئة المائية (نهر، حوض، بئر، سحاب).
* `E_WATER_DYNAMICS`: حركة فيزيائية أو صوت ماء (خرير، فوران، طفو، سيحان).
* `E_WATER_EFFECT`: أثر ناجم عن الماء (بلل، غرق، رطوبة، نضارة، صدأ).
* `E_METAPHORICAL_EXT`: توسع مجازي مثبت معجمياً مشتق من حالة مائية (الجود $\leftarrow$ فيض الماء).

##### الطبقة 2: العلاقات الصرفية (Morphological Edges)
* `E_ROOT_DERIVATION`: اشتقاق صيغة من جذر معجمي محدد.
* `E_PATTERN_APPLICATION`: انطباق وزن صرفي ودلالته على لفظ.
* `E_INFLECTIONAL_VARIANT`: علاقة بين مفرد وجمعه، أو فعل ومصدره.

##### الطبقة 3: العلاقات الصوتية (Phonetic Edges)
* `E_PHONETIC_IDENTITY`: تطابق صوتي تاريخي تام.
* `E_REGULAR_SOUND_SHIFT`: انتقال صوتي منتظم ومبرر بقانون صوتي تاريخي سامي معتمد.
* `E_ARABIC_METATHESIS`: قلب مكاني مقيد موثق في فصيح كلام العرب (جذب $\leftrightarrow$ جبذ).
* `E_SPURIOUS_SUBSTITUTION`: **إبدال صوتي اعتباطي غير مقيس (يُوسم تلقائياً كعلاقة غير مقبولة أو ذات كلفة عقابية قصوى)**.

##### الطبقة 4: العلاقات التاريخية والمقارنة (Historical & Comparative Edges)
* `E_PROTO_SEMITIC_COGNATE`: اشتراك موثق بنقوش اللغات السامية المقارنة مع الجذر البدائي المشترك (*Proto-Semitic Root*).
* `E_EPIGRAPHIC_ATTESTATION`: ثبوت اللفظ في النقوش العربية والمسندية القديمة.
* `E_LEXICAL_BORROWING`: اقتراض لغوي تاريخي من لغات مجاورة غير سامية أو آرامية متأخرة.

##### الطبقة 5: العلاقات الاستدلالية والتفنيدية (Epistemic & Falsification Edges)
* `E_SUPPORTS`: شاهد أو قاعدة تؤيد صحة علاقة اشتقاقية أو دلالية.
* `E_CONTRADICTS`: شاهد أو قرينة تنقض العلاقة المقترحة وتعزز تفسيراً بديلاً.
* `E_COMPETING_ORIGIN`: إحالة إلى أصل معجمي منافس أقوى تاريخياً (مثل الأصل الصخري أو الناري).

#### مصفوفة قيود وقواعد الانتقال (Edge Traversal Rules)
1. **قيد الحفاظ على السند:** لا يجوز الانتقال عبر علاقة اشتقاق تاريخي `E_REGULAR_SOUND_SHIFT` ما لم تكن متصلة بعقدة قانون صوتي `V_RULE` مستندة إلى شاهد مقارن.
2. **منع القفز فوق الدلالة:** لا يجوز ربط جذر $r_1$ بمفهوم $c_1$ مباشرة؛ بل يجب أن يمر المسار بالترتيب الإلزامي التالي:
   $$r_1 \xrightarrow{\text{DERIVES}} u_1 \xrightarrow{\text{EXPRESSES}} s_1 \xrightarrow{\text{MAPS\_TO}} c_1$$
3. **الحد الأقصى للعمق المسموح به ($k\text{-hops}$):** يُحظر قبول أي مسار يتجاوز 4 انتقالات بين الجذر ومفهوم الماء، نظراً لأن زيادة عدد القفزات تؤدي رياضياً إلى تلاشي الدلالة واستدعاء المصادفة العشوائية.

---

### المخرج C: النموذج الرياضي الموحد لتقييم المسارات واليقين البايزي

#### 1. دالة تسجيل المسار المرجحة (Path Quality Score)
لكل مسار استكشافي $P = (v_0, e_1, v_1, \dots, e_k, v_k)$ يربط الجذر بعقدة الماء المركزية، يُحسب المعامل الإجمالي:

$$\operatorname{Score}(P) = \operatorname{Evidence}(P) - \lambda_{\text{comp}} \cdot \operatorname{Complexity}(P) - \lambda_{\text{contra}} \cdot \operatorname{Contradictions}(P)$$

حيث:
* $\operatorname{Evidence}(P)$: مجموع قوى الإثبات للأدلة والشواهد على طول المسار:
  $$\operatorname{Evidence}(P) = \sum_{i=1}^{k} w(e_i) \cdot \operatorname{Rel}(v_{i-1}, v_i) \cdot \operatorname{Conf}(e_i)$$
  - $w(e_i) \in [0, 1]$: وزن نوع العلاقة (الاشتقاق الموثق بنقش = 1.0، التوسع المجازي المعجمي = 0.7، التحول المقيس = 0.6، الفرضية اللغوية = 0.2).
  - $\operatorname{Rel}$: درجة الموثوقية التوثيقية للمصدر التاريخي (معاجم القرون الأولى والنقوش = 1.0، مصادر متأخرة = 0.5).
  - $\operatorname{Conf}$: درجة اكتمال الشاهد وعدم اضطرابه.

* $\operatorname{Complexity}(P)$: دالة تعقيد المسار وتراكم التحولات:
  $$\operatorname{Complexity}(P) = k + \alpha \sum_{j \in \text{PhoneticShifts}(P)} \operatorname{Cost}(j)$$
  - $k$: عدد الحواف (طول المسار).
  - $\operatorname{Cost}(j)$: كلفة التحول الصوتي. إذا كان التحول غير منتظم في قوانين الفونولوجيا السامية، تُفرض كلفة عقابية باهظة ($\operatorname{Cost}(j) \ge 10.0$) تسقط المسار إلى النطاق السالب.

* $\operatorname{Contradictions}(P)$: جزاء الشواهد المعاكسة والاعتراضات:
  $$\operatorname{Contradictions}(P) = \sum_{m \in \text{CounterEvidence}(P)} \mu_m \cdot \operatorname{Severity}(m)$$
  - $\operatorname{Severity}(m) \in [1, 5]$: شدة التناقض (ثبوت معنى بيئي صلب مناقض تماماً، كالأرض الصلبة أو النار الحارقة، يُعطى درجة 5).
  - $\lambda_{\text{comp}} = 0.8, \lambda_{\text{contra}} = 2.5$: معاملات الترجيح الجزائية المحايدة تجريبياً لمنع الانحياز.

#### 2. الاستدلال البايزي الصارم لحساب احتمال صحة المسار (Posterior Probability)
لحساب احتمال كون العلاقة المائية للجذر $r$ حقيقة تاريخية أصلية ($H_{\text{water}}$) في مقابل الأصل البديل المنافس ($H_{\text{alt}}$) أو الصدفة ($H_{\text{chance}}$):

$$P(H_{\text{water}} \mid \mathcal{D}) = \frac{P(\mathcal{D} \mid H_{\text{water}}) \cdot P(H_{\text{water}})}{P(\mathcal{D} \mid H_{\text{water}}) P(H_{\text{water}}) + P(\mathcal{D} \mid H_{\text{alt}}) P(H_{\text{alt}}) + P(\mathcal{D} \mid H_{\text{chance}}) P(H_{\text{chance}})}$$

* **معايرة الاحتمال المسبق ($Prior$):**
  - نحدد احتمالاً مسبقاً محايداً للأصل المائي للجذور العامة غير المائية ظاهرياً: $P(H_{\text{water}}) = 0.05$.
  - يُحدد الاحتمال المسبق للأصل المائي للجذور ذات الدلالة السائلة الواضحة: $P(H_{\text{water}}) = 0.80$.
* **حساب دالة الإمكان ($\text{Likelihood} - P(\mathcal{D} \mid H)$):**
  - تعتمد على انتظام التحولات الصوتية ووجود شواهد أركيولوجية ونقشية متزامنة، بحيث يتلاشى $P(\mathcal{D} \mid H_{\text{water}})$ عند غياب السند الصوتي المقارن.

#### 3. مستويات الفصل الثلاثية (Tripartite Classification)
* **المسار الموثق تاريخياً:** $\operatorname{Score}(P) \ge 3.5 \quad \text{AND} \quad P(H_{\text{water}} \mid \mathcal{D}) \ge 0.85$ (وجود شواهد ونقوش وتحولات منتظمة).
* **المسار الدلالي المقبول داخلياً (مجاز معجمي):** $1.5 \le \operatorname{Score}(P) < 3.5$ مع خلوه من التعارضات الصوتية والتاريخية.
* **المسار المرفوض/الزائف:** $\operatorname{Score}(P) < 1.5 \quad \text{OR} \quad \operatorname{Contradictions}(P) \ge 3.0$ (يُصنف كاشتقاق شعبي وهمي).

---

### المخرج D: مخطط قاعدة البيانات القابلة للتدقيق (Relational & Provenance Schema)

يتبع النظام تصميم قواعد البيانات العياري المتوافق مع شروط الحفظ التاريخي الكامل وعدم قابلية التعديل للمسارات المرفوضة (*Append-Only Audit Log*).

```sql
-- 1. جدول الجذور اللغوية
CREATE TABLE lex_roots (
    root_id VARCHAR(64) PRIMARY KEY, -- مثال: "r_x_l_d", "r_m_w_h"
    radicals VARCHAR(32) NOT NULL,    -- الأحرف المجردة: "خ-ل-د"
    radical_count INT NOT NULL,       -- 2, 3, 4
    proto_semitic_form VARCHAR(64),   -- الجذر في السامية الأم إن وجد
    is_disputed BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
);

-- 2. جدول الألفاظ والصيغ المشتقة
CREATE TABLE lex_lemmas (
    lemma_id VARCHAR(64) PRIMARY KEY,
    root_id VARCHAR(64) REFERENCES lex_roots(root_id),
    vocalized_form VARCHAR(128) NOT NULL, -- الشكل المشكول بالكامل: "خَالِد"
    normalized_form VARCHAR(128) NOT NULL, -- للبحث والتطبيع
    pos_tag VARCHAR(32),                   -- اسم فاعل، صفة مشبهة، فعل ماض
    morph_pattern VARCHAR(64)              -- الوزن: "فَاعِل"
);

-- 3. جدول المعاني الدلالية الدقيقة
CREATE TABLE lex_senses (
    sense_id VARCHAR(64) PRIMARY KEY,
    lemma_id VARCHAR(64) REFERENCES lex_lemmas(lemma_id),
    sense_definition TEXT NOT NULL,
    semantic_domain VARCHAR(64), -- "LIQUID", "SOLIDITY", "DURATION", "FIRE"
    source_lexicon VARCHAR(128)  -- اسم المعجم المعتمد: "لسان العرب"، "مقاييس اللغة"
);

-- 4. جدول المفاهيم الأنطولوجية التجريدية
CREATE TABLE onto_concepts (
    concept_id VARCHAR(64) PRIMARY KEY, -- مثال: "C_WATER_RESERVOIR", "C_SOLID_GROUND"
    concept_label_ar VARCHAR(128) NOT NULL,
    concept_label_en VARCHAR(128) NOT NULL,
    parent_concept_id VARCHAR(64) REFERENCES onto_concepts(concept_id),
    is_water_domain BOOLEAN NOT NULL DEFAULT FALSE
);

-- 5. جدول القواعد الصوتية والتحولات التاريخية
CREATE TABLE phonology_rules (
    rule_id VARCHAR(64) PRIMARY KEY,
    source_sound VARCHAR(8) NOT NULL,  -- الصوت الأصلي: "x" (خ)
    target_sound VARCHAR(8) NOT NULL,  -- الصوت المحول إليه: "k" (ك)
    environment VARCHAR(128),          -- البيئة الصوتية المشروطة
    is_regular_shift BOOLEAN NOT NULL, -- هل هو تحول مطرد أم شاذ؟
    semitic_language_context VARCHAR(64), -- "Proto-Semitic to Arabic", "Aramaic-Arabic"
    cost_penalty NUMERIC(4,2) NOT NULL  -- الكلفة الرياضية (0.0 للمطرد، 15.0 للشاذ)
);

-- 6. جدول الشواهد والنصوص التاريخية المؤرخة
CREATE TABLE attestations (
    attestation_id VARCHAR(64) PRIMARY KEY,
    text_content TEXT NOT NULL,
    attestation_type VARCHAR(32) NOT NULL, -- 'INSCRIPTION', 'POETRY_PRE_ISLAMIC', 'QURAN', 'HADITH', 'LEXICON'
    chronological_era VARCHAR(64),          -- 'PRE_ISLAMIC', 'EARLY_ISLAMIC', 'PROTO_SEMITIC'
    dating_estimate_bce_ce INT,             -- السنة التقديرية
    source_document VARCHAR(256) NOT NULL,  -- عنوان المرجع والباب ورقم الصفحة
    reliability_score NUMERIC(3,2) NOT NULL -- [0.0 - 1.0]
);

-- 7. جدول العلاقات المعرفية في الرسم البياني (Graph Edges Table)
CREATE TABLE graph_edges (
    edge_id VARCHAR(64) PRIMARY KEY,
    source_node_id VARCHAR(64) NOT NULL,
    target_node_id VARCHAR(64) NOT NULL,
    edge_type VARCHAR(64) NOT NULL,         -- 'E_DIR_WATER_SENSE', 'E_METAPHORICAL_EXT', إلخ
    confidence_score NUMERIC(4,3) NOT NULL,
    phonetic_rule_id VARCHAR(64) REFERENCES phonology_rules(rule_id),
    is_hypothetical BOOLEAN DEFAULT FALSE,
    is_falsified BOOLEAN DEFAULT FALSE,
    rejection_reason TEXT
);

-- 8. جدول ربط الحواف بالشواهد الإثباتية والمعاكسة
CREATE TABLE edge_evidences (
    evidence_link_id VARCHAR(64) PRIMARY KEY,
    edge_id VARCHAR(64) REFERENCES graph_edges(edge_id),
    attestation_id VARCHAR(64) REFERENCES attestations(attestation_id),
    polarity VARCHAR(16) NOT NULL, -- 'SUPPORTING' أو 'CONTRADICTING'
    impact_weight NUMERIC(3,2) NOT NULL
);

-- 9. سجل التدقيق غير القابل للحذف (Audit Trail & Falsification Log)
CREATE TABLE hypothesis_audit_log (
    log_id BIGSERIAL PRIMARY KEY,
    hypothesis_id VARCHAR(64) NOT NULL,
    action_type VARCHAR(32) NOT NULL, -- 'GENERATED', 'VERIFIED', 'PENALIZED', 'REJECTED'
    evaluator_component VARCHAR(64) NOT NULL, -- 'PhoneticEngine', 'FalsificationLayer'
    previous_score NUMERIC(5,3),
    new_score NUMERIC(5,3),
    detailed_decision_log JSONB NOT NULL,
    timestamp TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,
    cryptographic_checksum VARCHAR(64) -- بصمة SHA-256 لمنع التلاعب بالسجل
);
```

---

### المخرج E: خوارزمية البحث المقيد والتفنيد الصارم (Search & Falsification Algorithms)

#### 1. خوارزمية البحث الموجه والتوليد المقيد (Constrained Bidirectional Search)

```python
def search_aquatic_paths(
    target_root: str,
    max_depth: int = 4,
    max_cost_threshold: float = 12.0
) -> List[Path]:
    """
    يبحث عن مسارات محتملة تربط الجذر بمفهوم الماء المركزي
    بشرط ألا يتجاوز العمق 4 وألا تتجاوز التكلفة الصوتية الحد الحرج.
    """
    priority_queue = PriorityQueue()
    start_nodes = get_lemmas_and_senses(target_root)
    
    for node in start_nodes:
        initial_path = Path(nodes=[node], edges=[], cost=0.0)
        priority_queue.push(initial_path, priority=0.0)
        
    valid_paths = []
    
    while not priority_queue.is_empty():
        current_path = priority_queue.pop()
        current_node = current_path.last_node
        
        # شرط التوقف بالوصول لمفهوم الماء المباشر
        if current_node.is_root_water_concept():
            valid_paths.append(current_path)
            continue
            
        if len(current_path.edges) >= max_depth:
            continue
            
        neighbors = get_typed_neighbors(current_node)
        for edge, next_node in neighbors:
            # 1. التدقيق الفونولوجي الصارم:
            if edge.type == 'PHONETIC_SHIFT':
                shift_rule = edge.get_phonetic_rule()
                if not shift_rule.is_regular:
                    # فرض عقوبة صوتية كبرى على الإبدال غير المقيس
                    edge_cost = shift_rule.cost_penalty # >= 10.0
                else:
                    edge_cost = shift_rule.cost_penalty # < 1.5
            else:
                edge_cost = 0.2 # تكلفة الانتقال الصرفي/الدلالي
                
            accumulated_cost = current_path.cost + edge_cost
            if accumulated_cost > max_cost_threshold:
                # تقليم المسار (Pruning) فوراً لمنع التوليد العشوائي
                log_rejected_branch(current_path, edge, "EXCEEDED_MAX_PHONETIC_COST")
                continue
                
            new_path = current_path.append(edge, next_node, accumulated_cost)
            priority_queue.push(new_path, priority=accumulated_cost)
            
    return valid_paths
```

#### 2. خوارزمية التفنيد المستقل وإسقاط الروابط الزائفة (Falsification Algorithm)

```python
def falsify_hypothesized_path(path: Path) -> FalsificationReport:
    """
    طبقة التحقق المستقلة: تحاول نقض المسار بالبحث عن تفاسير منافسة
    وشواهد معجمية ونقشية أصلية تدحض الرابط المائي.
    """
    report = FalsificationReport(path=path)
    
    # 1. اختبار التفسير التنافسي الأصيل (Competing Explanation Test)
    competing_origins = query_lexical_domains(path.target_root)
    # إذا كان الجذر موثقاً في أصول البيئة الصلبة (صخر، حجارة، أرض غليظة)
    if "SOLID_EARTH" in competing_origins or "STONE" in competing_origins:
        report.add_counter_evidence(
            severity=5.0,
            source="Ibn Faris - Maqayis al-Lughah",
            details=f"Root {path.target_root} is an established primary root for hardness/solidity."
        )
        
    # 2. اختبار القانون الصوتي التاريخي (Comparative Phonetic Check)
    for edge in path.edges:
        if edge.type == 'PHONETIC_SHIFT':
            p_rule = edge.get_phonetic_rule()
            if p_rule.source_sound == 'x' and p_rule.target_sound == 'k': # إبدال الخاء كافاً
                # التحقق في اللغات السامية الشقيقة (الأكدية، العبرية، الأرامية، الجعزية)
                cognates = get_semitic_cognates(path.target_root)
                if not any(c.sound == 'k' for c in cognates):
                    report.add_phonetic_violation(
                        severity=5.0,
                        rule="Velar-Fricative to Stop irregular alternation without conditioning environment",
                        verdict="SPURIOUS_SUBSTITUTION"
                    )
                    
    # 3. اختبار المقارنة بالتحكم العشوائي (Baseline Permutation Test)
    # هل يمكن لنفس الحيل الصوتية أن تربط الكلمة بمفهوم 'النار' أو 'الحجر'؟
    stone_path = test_alternative_baseline(path.target_root, target_concept="STONE")
    if stone_path.cost <= path.cost:
        report.add_baseline_hazard(
            details="Path is non-discriminative; connects with equal or less cost to non-water concepts."
        )
        
    # احتساب النتيجة النهائية للتفنيد
    total_penalty = sum(ce.severity for ce in report.counter_evidences)
    if total_penalty >= 5.0 or report.has_phonetic_violation:
        report.status = "REJECTED_AS_SPURIOUS"
    else:
        report.status = "SURVIVED_FALSIFICATION"
        
    return report
```

---

### المخرج F: بروتوكول التقييم والتجارب العلمية المعيارية (Evaluation & Benchmarks)

#### 1. تكوين المجموعات المرجعية المعيارية ($N=500$ جذر)
تُبنى بيانات الاختبار من خمس فئات حاسمة ومتوازنة:
* **المجموعة A (مائية صريحة - Positive Controls - 100 جذر):** جذور الماء والسيولة المعترف بها إجماعاً ($\sqrt{\text{م-و-ه}}$، $\sqrt{\text{س-ي-ل}}$، $\sqrt{\text{ن-ض-خ}}$، $\sqrt{\text{غ-ر-ق}}$، $\sqrt{\text{م-ط-ر}}$).
* **المجموعة B (مشتقات مجازية بيئية موثقة - 100 جذر):** كلمات تحولت دلالاتها من الماء إلى المعنويات مع توثيق معجمي معتمد ($\sqrt{\text{ف-ي-ض}}$، $\sqrt{\text{غ-م-ر}}$، $\sqrt{\text{ر-و-ي}}$).
* **المجموعة C (أصول منافسة صلبة/نارية - Negative Controls - 100 جذر):** جذور تدل في أصلها السامي على اليبوسة، الحجر، النار ($\sqrt{\text{ح-ج-ر}}$، $\sqrt{\text{ص-ل-د}}$، $\sqrt{\text{ق-د-ح}}$، $\sqrt{\text{ج-م-د}}$).
* **المجموعة D (ألفاظ ذات اشتقاقات وتلفيقات شعبية شائعة - Folk Etymology Tests - 100 جذر):** الكلمات التي رُكبت لها أصول مائية دون سند صوتي معجمي (مثل دعوى: $\sqrt{\text{خ-ل-د}}$ من $\sqrt{\text{ك-ل-د}}$).
* **المجموعة E (أصول خلافية ومبهمة - Disputed/Unknown - 100 جذر):** جذور مجهولة الأصل في الساميات لدراسة قدرة النظام على التوقف والتصنيف بـ «عدم كفاية الأدلة».

#### 2. النماذج المرجعية المقابلة (Baseline Models)
يُقارن أداء `AALG` بأربعة نماذج مرجعية:
1. **النموذج العشوائي الصوتي (Unconstrained Phonetic Permutation Baseline):** يسمح بتبديل الحروف المتشابهة دون قيود، لقياس حجم الروابط الزائفة المتولدة.
2. **النموذج الدلالي العام (Generic WordNet Baseline):** يعتمد القرب في فضاء المتجهات المعجمية العامة دون تركيز على الماء.
3. **النموذج المعجمي التقليدي (Dictionary-Lookup Baseline):** يكتفي بما نص عليه صراحة ابن منظور والزبيدي وابن فارس.
4. **نموذج الحجر/النار المقابل (Mirror Concept Baseline):** يختبر مدى قدرة نفس القواعد على ربط كلمات المعجم بـ «الأرض والحجر» لمعايرة التحيز الانحيازي.

#### 3. معايير النجاح والفشل الكمية الصارمة (Acceptance Thresholds)
* **دقة كشف العلاقات الزائفة (Spurious Edge Rejection Rate):** $\ge 98\%$ على المجموعة المرجعية D والمجموعة C.
* **الحساسية على العلاقات المائية الصريحة (Recall on Positive Controls):** $\ge 95\%$ على المجموعة A.
* **معدل الإيجابية الكاذبة (False Positive Rate):** $\le 2\%$ عبر إحباط المسارات التي تفتقر لسند صوتي وتاريخي.
* **استقرار النتائج (Perturbation Invariance):** تباين النتائج أقل من $5\%$ عند إحداث تغيير بنسبة $\pm 15\%$ في أوزان المعاملات الرياضية ($\lambda$).
* **معيار الفشل الصريح للمشروع:** إذا ربط النظام جذور المجموعة C (الصلابة والنار) بمفهوم الماء بنسبة تزيد على $5\%$ بدرجات دعم مرتفعة، يُعد النظام معيباً ومتحيزاً تأكيدياً وتتوقف التجارب لإعادة المعايرة.

---

### المخرج G: بنية المشروع البرمجي المقترحة (File Architecture)

```
aquatic_arabic_lexical_graph/
├── pyproject.toml                     # تعريف الحزم والاعتماديات
├── README.md                          # دليل التثبيت وإعادة الإنتاج
├── config/
│   ├── graph_config.yaml             # إعدادات كلفة الحواف والأوزان
│   └── falsification_rules.yaml      # قيود التفنيد والقوانين الصوتية
├── data/
│   ├── raw/                           # المعاجم ونصوص النقوش بصيغ TEI XML
│   │   ├── maqayis_allughah.xml
│   │   ├── lisan_alarab.xml
│   │   └── semitic_inscriptions.json
│   ├── processed/                     # قواعد البيانات المجهزة بصيغة Parquet/DuckDB
│   │   ├── arabic_roots.parquet
│   │   └── phonetic_inventory.parquet
│   └── gold_standards/                # المجموعات المرجعية للاختبار (500 جذر)
│       └── benchmark_roots_500.json
├── database/
│   ├── migrations/                    # ملفات ترحيل جداول PostgreSQL
│   │   └── 001_initial_schema.sql
│   └── db_manager.py                  # إدارة الاتصال والتدقيق المشفر
├── src/
│   ├── __init__.py
│   ├── phonology/                     # محرك الفونولوجيا السامية المقارنة
│   │   ├── sound_inventory.py        # الأصوات السامية وخصائصها الفيزيائية
│   │   ├── regular_shifts.py         # التحولات الصوتية المنتظمة
│   │   └── phonetic_cost.py          # حساب مصفوفة الكلفة الصوتية
│   ├── morphology/                    # التحليل الصرفي وتجريد الأوزان
│   │   ├── root_extractor.py
│   │   └── pattern_analyzer.py
│   ├── graph/                         # نواة الرسم البياني والعمليات الطوبولوجية
│   │   ├── heterogeneous_graph.py    # بناء شبكة G = (V, E, T, A)
│   │   ├── path_finder.py            # البحث المقيد ومحدد العمق
│   │   └── graph_exporters.py        # تصدير بصيغ GraphML, JSON-LD
│   ├── falsification/                 # محرك التفنيد والنماذج المنافسة
│   │   ├── counter_evidence.py       # استدعاء الشواهد المضادة
│   │   ├── baseline_comparator.py    # المقارنة بفرضيات الحجر والنار
│   │   └── phonetic_validator.py     # كشف الإبدالات التلفيقية
│   ├── scoring/                       # النموذج الرياضي والاحتمال البايزي
│   │   ├── bayesian_evaluator.py     # حساب Posterior Probability
│   │   └── path_scoring.py           # حساب معادلة Score(P)
│   └── visualization/                 # التصدير المرئي والواجهة
│       ├── cytoscape_adapter.py      # تصدير التنسيقات لـ Cytoscape.js
│       └── dashboard_api.py          # واجهة REST API للاستكشاف
└── tests/
    ├── test_phonological_engine.py    # التحقق من دقة القوانين الصوتية
    ├── test_falsification_layer.py    # اختبار إسقاط دعوى "خالد/كلدة"
    ├── test_positive_controls.py      # اختبار إثبات "سيل/موه"
    └── test_reproducibility.py        # اختبار استقرار نتائج البايزي
```

---

### المخرج H: النموذج الأولي المصغر وحالات دراسية حاسمة (Concrete Cases)

#### الحالة 1: جذر مائي أصيل مثبت بالنقوش المقارنة ($\sqrt{\text{م-و-ه}}$ $\leftarrow$ ماء)
* **المسار في الشبكة:**
  $$\text{Root}(\text{م-و-ه}) \xrightarrow{\text{DERIVES}} \text{Lemma}(\text{مَاءٌ}) \xrightarrow{\text{EXPRESSES}} \text{Sense}(\text{الجوهر السائل}) \xrightarrow{\text{MAPS\_TO}} \text{Concept}(\text{WATER})$$
* **البيانات المقارنة والشواهد:**
  - تطابق في اللغات السامية: العبرية (*máyim* - מַיִם)، الأكدية (*mū* / *māyū*)، الأوغاريتية (*my*)، السريانية (*mayyā* - ܡܝ̈ܐ)، السبئية (*م و هـ*).
  - قانون صوتي: تطابق أصوات الشفاهي الهاوي السامي المشترك (*Proto-Semitic* $\text{*ma'y-}$ / $\text{*mahw-}$).
* **تقييم النموذج:**
  - $\operatorname{Evidence}(P) = 1.0 \times 1.0 + 1.0 \times 1.0 = 2.0$
  - $\operatorname{Complexity}(P) = 2 + 0.0 = 2$
  - $\operatorname{Contradictions}(P) = 0.0$
  - $\operatorname{Score}(P) = 2.0 - (0.8 \times 2) - 0 = +0.4$ (مع ثبوت $P(H_{\text{water}} \mid \mathcal{D}) = 0.999$).
* **الحكم والتصنيف:** **اشتقاق مائي تاريخي سامي قطعي ومثبت.**

#### الحالة 2: توسع دلالي مجازي داخلي موثق معجمياً ($\sqrt{\text{غ-م-ر}}$ $\leftarrow$ غَمْر / غَمَرَ)
* **المسار في الشبكة:**
  $$\text{Root}(\text{غ-م-ر}) \xrightarrow{\text{DERIVES}} \text{Lemma}(\text{غَمْر}) \xrightarrow{\text{EXPRESSES}} \text{Sense}(\text{الماء الكثير المغطي لما تحته})$$
  $$\xrightarrow{\text{METAPHORICAL\_EXT}} \text{Lemma}(\text{غَمَرَ فلانٌ فلاناً بمعروفه}) \xrightarrow{\text{MAPS\_TO}} \text{Concept}(\text{ABUNDANT\_BENEVOLENCE})$$
* **التحقق المعجمي:**
  - نص ابن فارس في *مقاييس اللغة*: «الغين والميم والراء أصل صحيح يدل على تغطية الشيء وستره... ومنه الغَمْر: الماء الكثير؛ لأنه يستر ما تحته، ثم كثر حتى سُمي كل مجاوزة في حدٍّ غَمْرة».
  - لم يحدث أي إبدال صوتي، والمسار مدعوم بتسلسل معجمي داخلي معترف به عند فصحاء العرب.
* **تقييم النموذج:**
  - $\operatorname{Score}(P) = +2.45$
  - $\operatorname{Contradictions}(P) = 0.0$
  - $P(H_{\text{water\_metaphor}} \mid \mathcal{D}) = 0.89$
* **الحكم والتصنيف:** **توسع دلالي مجازي موثق ينطلق من صفة الماء الفيزيائية.**

#### الحالة 3: الفحص الاستقصائي لدعوى اشتقاق «خالد» من «كالد / كلدة / ماء راكد»
هذه هي الحالة المنسوبة في الروايات الشفهية إلى الأديب عبد الله نور، والتي يزعم فيها أن اسم *خالد* مشتق من *الكلدة* بمعنى حوض الماء الراكد.

```
[مزاعم الفرضية غير المدعومة]
خ-ل-د  ===(إبدال تعسفي خ -> ك)===>  ك-ل-د  ===(تفسير مختلق)===>  حوض ماء راكد
                                       |
                                 [حقيقة المعجم]
                                       |
                                       v
                     الصلابة والغلظة واليبوسة (عكس الماء تماماً)
```

1. **فحص التحول الصوتي المقترح ($\text{خ} \leftrightarrow \text{ك}$):**
   - الحرفان: الخاء ($\text{/x/}$ أو $\text{/χ/}$) احتكاكي لهوي مهموس، والكاف ($\text{/k/}$) وقفي طبقي مهموس.
   - في الفونولوجيا التاريخية السامية، هما صوتان فونيمان أصيلان مستقلان من السامية الأم (*Proto-Semitic* $\text{*k}$ و $\text{*x}$).
   - لا توجد قاعدة صوتية منتظمة في تاريخ الساميات أو لهجات العرب الفصحى تحول الخاء كافاً دون شرط مجاورة صوتية شديدة الندرة.
   - كلفة التحول الصوتي المحتسبة: $\operatorname{Cost}(\text{Shift}) = 15.0$ (تحول شاذ غير مقيس).
2. **فحص التحقيق المعجمي لمادة (ك-ل-د):**
   - نص ابن فارس (*مقاييس اللغة*): «الكاف واللام والدال كلمة تدل على **الصَّلابَةِ** في الشيء؛ فالكَلَدَةُ: **القطعة من الأرض الغليظة**... وتكلّد الإنسان: غلظ لحمه».
   - نص ابن منظور (*لسان العرب*): «الكَلَدَةُ: الأرض الغليظة الصُّلبة الحجارة... وضبٌّ كلدة: لا يحفر إلا في أرض صلبة».
   - لم يذكر أي معجم عربي (العين، الجمهرة، التهذيب، الصحاح، المقاييس، المحكم، اللسان، التاج) على الإطلاق أن «الكلدة» تعني «حوض ماء» أو «ماء راكد»!
3. **تقرير طبقة التفنيد المحوسب:**
   - شواهد مضادة شديدة الخطورة: دلالة المادة المعجمية هي الصلابة والحجارة واليبوسة (تناقض حاد مع مفهوم السائل المائي: $\text{Severity} = 5.0$).
   - انتهاك صوتي: افتراض إبدال غير مقيس ($\text{Severity} = 5.0$).
4. **حساب التقييم الرياضي في النظام:**
   - $\operatorname{Evidence}(P) = 0.1$ (مجرد تشابه كتابي متخيل).
   - $\operatorname{Complexity}(P) = 2 + (0.8 \times 15.0) = 14.0$
   - $\operatorname{Contradictions}(P) = 5.0 \text{ (دلالي)} + 5.0 \text{ (صوتي)} = 10.0$
   - $$\operatorname{Score}(P) = 0.1 - (0.8 \times 14.0) - (2.5 \times 10.0) = 0.1 - 11.2 - 25.0 = \mathbf{-36.1}$$
   - $P(H_{\text{water}} \mid \mathcal{D}) < 10^{-6}$
5. **الحكم والتصنيف النهائي للنظام:**
   **مسار تلفيقي زائف بامتياز (Falsified Spurious Folk-Etymology)**؛ ترفض الشبكة إدراجه كحافة حقيقية، ويسجل في سجل التدقيق التاريخي (`hypothesis_audit_log`) كنموذج للاشتقاق الشعبي الانطباعي غير المستند إلى لغة أو تاريخ.

#### الحالة 4: جذر ذو أصل صلب أصيل لا صلة له بالماء ($\sqrt{\text{ح-ج-ر}}$ $\leftarrow$ حَجَر)
* **المسار المقترح:** محاولة ربط الحجر بالماء عن طريق التصلب أو الرواسب المائية.
* **فحص المعاجم والمقارن:**
  - الجذر السامي المشترك يدل على التحويز والمنع والصلابة (*Proto-Semitic* $\text{*ḥ-g-r}$ - ربط، أحاط، صخر).
  - لا توجد شواهد اشتقاقية وسيطة تربطه بالماء في النقوش القديمة.
* **تقييم النظام:**
  - $\operatorname{Score}(P) = -8.4$
  - يعلن النظام صراحة: **«الجذر حجري/تحديدي أصيل، ولا يوجد مسار مائي مدعوم بأدلة»**.

---

### المخرج I: خطة التنفيذ المرحلية وجدول الإنجاز (Implementation Roadmap)

| المرحلة | الأهداف الرئيسية | المخرجات الهندسية | شروط القبول وضبط الجودة (Gate Acceptance Criteria) |
|---|---|---|---|
| **المرحلة 1: التأسيس والبنية التحتية** (الشهور 1-3) | استيراد المعاجم والنقوش وبناء قاعدة البيانات العلائقية ومخزن الرسوم البيانية. | - بيئة PostgreSQL + DuckDB.<br>- هيكل بيانات المعاجم منظماً بصيغة JSON-LD.<br>- واجهات الربط الصرفي. | اكتمال استيراد 5 معاجم رئيسية وتحقيق 10,000 جذر عربي معزولة عن أي فرضيات مسبقة. |
| **المرحلة 2: الفونولوجيا والمحرك الصرفي** (الشهور 4-6) | ترميز قواعد الفونولوجيا السامية وجداول التحول الصوتي وحساب كلفة المسافات الصوتية. | - حزمة `phonology_rules`.<br>- خوارزمية قياس كلفة التحول الصوتي.<br>- معجم الجذور السامية المقارنة. | اجتياز اختبارات المطابقة الصوتية على 500 جذر سامي موثق بنسبة دقة $\ge 99\%$. |
| **المرحلة 3: طبقة التفنيد والبحث المقيد** (الشهور 7-9) | بناء محرك البحث $k\text{-hops}$ وطبقة التحقق التنافسي ونماذج الحجر والنار المقابلة. | - محرك `search_aquatic_paths`.<br>- خوارزميات كشف التناقض المعجمي.<br>- خط أنابيب التدقيق الآلي. | قدرة النظام على إسقاط 100% من المسارات التلفيقية المصطنعة في الاختبار القبلي. |
| **المرحلة 4: الاختبارات المعيارية والتقييم** (الشهور 10-12) | تطبيق البروتوكول التجريبي على الـ 500 جذر المرجعية وتطبيق التقييم البايزي. | - تقرير المعايرة الإحصائية.<br>- مصفوفة الارتباك (*Confusion Matrix*).<br>- تحليل الحساسية وتوليد $p\text{-values}$. | بقاء معدل الإيجابية الكاذبة أقل من $2\%$، وإثبات تفوق النموذج على خط الأساس العشوائي. |
| **المرحلة 5: الواجهة البصرية والنشر العلمي** (الشهور 13-15) | تطوير منصة الاستكشاف التفاعلية، وإتاحة التدقيق التاريخي، وتصدير النتائج مفتوحة المصدر. | - لوحة استكشاف ويب تفاعلية.<br>- واجهة برمجة تطبيقات (API).<br>- ورقة علمية محكمة للمؤتمرات الدولية. | قدرة أي باحث خارجي على إعادة تشغيل بيئة العمل وإنتاج نفس النتائج بنقرة واحدة عبر Docker. |

---

### المخرج J: سجل المخاطر العلمية والتقنية وإجراءات التحييد (Risk Register)

| الرمز | وصف الخطر | الأثر العلمي والتقني | إجراء التحييد الهندسي والمحاسبي الصارم |
|---|---|---|---|
| **RSK-01** | **الانحياز التأكيدي (Confirmation Bias)** نحو إيجاد روابط للماء مهما بعدت. | كارثي: فقدان المصداقية العلمية وتحويل النظام إلى أداة تلفيق لغوي. | - تشغيل **النموذج المقابل (Mirror Concept Model)** بالتوازي كشرط إلزامي.<br>- منع احتساب أي مسار يمتلك مساراً بديلاً مساوياً أو أقل تكلفة نحو مفهوم طبيعي آخر (كالحجر أو النار). |
| **RSK-02** | **الهلوسة وتلفيق الشواهد عبر النماذج اللغوية (LLM Hallucination).** | كارثي: اختلاق شواهد وأشعار ومعاجم غير موجودة في كتب التراث. | - **حظر استخدام النماذج اللغوية التوليدية في طبقة الاستشهاد نهائياً**.<br>- حصر الاستشهاد بالبحث المباشر الحرفي في قواعد النصوص المعجمية المحققة عبر بصمة التحقق (Exact Match + Hash ID). |
| **RSK-03** | **التوليد المفرط عبر القلب والإبدال الصوتي (Acoustic Overgeneration).** | حرج: ربط أي كلمة بأي كلمة بواسطة قفزات صوتية غير مقيدة. | - تثبيت كلفة عقابية باهظة ($\text{Cost} \ge 10.0$) على أي إبدال غير مقيس في القوانين السامية.<br>- حصر عمق البحث الصوتي بنقلة واحدة فقط مشروطة بسند مقارن. |
| **RSK-04** | **الخلط بين التوسع الدلالي الداخلي والاشتقاق التاريخي الأصلي.** | متوسط: اعتبار الاستعارة المجازية دليلاً على أصل الكلمة عند النشأة الأولى. | - الفصل الرياضي والنوعي الصارم في تصنيف الحواف بين `E_METAPHORICAL_EXT` و`E_PROTO_SEMITIC_COGNATE`.<br>- منع ترقية المجاز إلى رتبة الأصل التاريخي دون نقش أركيولوجي يؤيده. |
| **RSK-05** | **التعميم السريع من عينات معجمية صغيرة غير ممثلة.** | عالي: إطلاق أحكام عامة على لسان العرب من خلال بضع عشرات من الجذور المختارة. | - اشتراط اختبار عينات عشوائية طبقية تغطي جميع مخارج الحروف العربية والجذور الثنائية والثلاثية والرباعية ومقارنتها إحصائياً بالفرضية الصفرية ($H_0$). |

---

## 3. معايير واجهة الاستكشاف والتصور البصري (Visualization & Exploration UI)

لتفادي التضليل، تعتمد واجهة النظام البصرية محددات هندسية تمنع الخلط بين الفرضية والحقيقة المعجمية:
1. **الترميز اللوني الدقيق للعلاقات:**
   - **اللون الأخضر المصمت:** علاقة اشتقاقية تاريخية سامية مثبتة بنقوش وشواهد قطعية.
   - **اللون الأزرق الداكن:** توسع دلالي مجازي موثق صراحة في أمهات المعاجم العربية القديمة.
   - **اللون البرتقالي المتقطع:** فرضية استكشافية قيد التحقق (تحت المراجعة المعجمية والصوتية).
   - **اللون الأحمر المزدوج:** **مسار مرفوض ومفند علمياً (يظهر التناقض الصوتي أو المعجمي بالتفصيل عند النقر عليه)**.
2. **شاشة المقارنة المتزامنة (Side-by-Side Verification Panel):**
   - عند استعراض أي مسار مائي مفترض لجذر ما، تُظهر الواجهة في الشطر المقابل التفسير المعجمي التقليدي المنافس، ومسار «الأرض والحجر»، لتوضيح ما إذا كان الرابط المائي ميزة فريدة أم مجرد توهم تطبيقي.
3. **تصدير شجرة التوثيق (Provenance Graph):**
   - توفير زر تحميل تقرير التحقيق التاريخي الكامل بصيغتي `PDF` مجهزة بالهوامش الأكاديمية وبصيغة `JSON-LD / GraphML` لتمكين الباحثين والمؤسسات اللسانية من مراجعة الحسابات الرياضية والقوانين الصوتية بشكل مستقل وغير قابل للشك.

---

## 4. الإجابة الحاسمة عن سؤال التصميم

**هل يستطيع نظام `AALG` بناء شبكة واسعة انطلاقاً من الماء مع الحفاظ على الصرامة التاريخية وتمييز الثابت من المتوهم؟**

**نعم، وبشكل حاسم وقابل لإعادة الإنتاج حاسوبياً وعلمياً؛** والسبب في ذلك هو أن النظام:
1. صُمم بحيث تكون **طبقة التفنيد والتحقق الصوتي المستقل مساوية في القوة المعمارية لمحرك توليد المسارات**.
2. لا يسمح بقبول أي رابط بمجرد «التشابه الحدسي» أو «التأويل الفلسفي»، بل يخضع التحولات لقوانين الفونولوجيا السامية، ويفصل المعنى المعجمي عن المفهوم الأنطولوجي، ويحسب الاحتمال البايزي الدقيق لكل خطوة.
3. يمتلك آلية رفض حاسمة تصنف الادعاءات غير المسندة (كنظرية اشتقاق خالد من الكلدة وحوض الماء) في خانة **«التلفيق والاشتقاق الشعبي الزائف»** مع تبيان الأدلة العكسية المفحمة رياضياً ومعجمياً، وفي الوقت ذاته يُبرز ويوثق الجذور التي ترتبط فيزيائياً ومجازياً بعنصر الماء في تراث وبيئة اللسان العربي بالدليل والبرهان.
