<!DOCTYPE html>
<html dir="rtl" lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>بنك امتحانات الفورامينفرا - جامعة سوهاج</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: linear-gradient(145deg, #eef2f5 0%, #e0e8f0 100%);
            font-family: 'Segoe UI', 'Tahoma', 'Traditional Arabic', 'Roboto', sans-serif;
            padding: 30px 20px;
            color: #1a2c3e;
        }
        .container {
            max-width: 1100px;
            margin: 0 auto;
        }
        .exam-header {
            background: #ffffff;
            border-radius: 42px;
            margin-bottom: 30px;
            box-shadow: 0 20px 35px rgba(0,0,0,0.1);
            overflow: hidden;
        }
        .header-top {
            background: linear-gradient(135deg, #1a4a6e 0%, #0f3552 100%);
            padding: 20px 30px;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
        }
        .title-section h1 {
            color: white;
            font-size: 1.5rem;
            margin-bottom: 8px;
            font-weight: 700;
        }
        .title-section p {
            color: #cbdbe6;
            font-size: 0.8rem;
        }
        .profile-image {
            flex-shrink: 0;
            background: white;
            border-radius: 50%;
            width: 75px;
            height: 75px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
            border: 3px solid #ffd966;
            overflow: hidden;
        }
        .profile-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .credit-name {
            background: #fef9e6;
            padding: 10px 25px;
            text-align: center;
            font-weight: 500;
            color: #9a7b3c;
            font-size: 0.85rem;
        }
        .credit-name span {
            font-weight: 700;
            color: #c47f2e;
        }
        .tabs-container {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            padding: 15px 20px 0 20px;
            background: white;
            border-bottom: 1px solid #e2e8f0;
        }
        .tab-btn {
            background: #e9ecef;
            border: none;
            padding: 10px 24px;
            border-radius: 30px 30px 0 0;
            font-size: 0.9rem;
            font-weight: bold;
            cursor: pointer;
            transition: 0.2s;
            color: #1a4a6e;
            font-family: inherit;
        }
        .tab-btn.active {
            background: #1a4a6e;
            color: white;
        }
        .progress-stats {
            display: flex;
            justify-content: space-between;
            background: #ffffffdc;
            backdrop-filter: blur(4px);
            padding: 10px 20px;
            border-radius: 50px;
            font-weight: bold;
            margin: 15px 20px;
            flex-wrap: wrap;
            gap: 10px;
        }
        .question-card {
            background: white;
            border-radius: 32px;
            margin: 0 20px 25px 20px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.05);
            overflow: hidden;
        }
        .question-header {
            background: #f8fafd;
            padding: 15px 22px;
            border-right: 6px solid #1a4a6e;
            display: flex;
            align-items: baseline;
            gap: 12px;
            flex-wrap: wrap;
        }
        .q-num {
            background: #1a4a6e;
            color: white;
            width: 36px;
            height: 36px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 30px;
            font-weight: bold;
            font-size: 0.9rem;
        }
        .q-text {
            font-size: 0.95rem;
            font-weight: 600;
            line-height: 1.45;
            flex: 1;
        }
        .options-area {
            padding: 15px 22px 10px 22px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .option {
            background: #f9fbfe;
            border: 1.5px solid #e0e9f2;
            border-radius: 100px;
            padding: 8px 18px;
            display: flex;
            align-items: center;
            cursor: pointer;
            transition: all 0.2s;
        }
        .option:hover {
            background: #eef3fc;
            border-color: #1a4a6e;
            transform: translateX(-3px);
        }
        .option input {
            margin-left: 12px;
            accent-color: #1a4a6e;
            cursor: pointer;
        }
        .option label {
            font-size: 0.85rem;
            font-weight: 500;
            cursor: pointer;
            flex: 1;
        }
        .option-row {
            display: flex;
            flex-direction: row;
            gap: 20px;
            flex-wrap: wrap;
        }
        .option-inline {
            background: #f9fbfe;
            border: 1.5px solid #e0e9f2;
            border-radius: 100px;
            padding: 8px 25px;
            display: inline-flex;
            align-items: center;
            cursor: pointer;
            transition: all 0.2s;
        }
        .option-inline:hover {
            background: #eef3fc;
            border-color: #1a4a6e;
        }
        .option-inline input {
            margin-left: 10px;
            accent-color: #1a4a6e;
            cursor: pointer;
        }
        .fill-input {
            width: calc(100% - 44px);
            margin: 15px 22px 10px 22px;
            padding: 10px 15px;
            border: 2px solid #e0e9f2;
            border-radius: 30px;
            font-size: 0.9rem;
            font-family: inherit;
        }
        .check-fill-btn {
            background: #1a4a6e;
            color: white;
            border: none;
            padding: 8px 20px;
            border-radius: 30px;
            cursor: pointer;
            font-weight: bold;
            margin: 0 22px 15px 22px;
        }
        .feedback {
            margin: 5px 22px 18px 22px;
            padding: 10px 15px;
            border-radius: 24px;
            font-size: 0.85rem;
            display: none;
        }
        .feedback.correct {
            background: #e0f7e8;
            border-right: 4px solid #2b7a4b;
            color: #145c33;
            display: block;
        }
        .feedback.wrong {
            background: #ffeaea;
            border-right: 4px solid #c7362b;
            color: #a11f14;
            display: block;
        }
        .action-bar {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 15px 0 35px;
            flex-wrap: wrap;
        }
        .btn {
            border: none;
            background: white;
            padding: 10px 24px;
            border-radius: 40px;
            font-weight: bold;
            font-size: 0.9rem;
            cursor: pointer;
            transition: 0.2s;
        }
        .btn-primary {
            background: #1a4a6e;
            color: white;
        }
        .btn-primary:hover {
            background: #0f3552;
            transform: scale(0.97);
        }
        .btn-outline {
            border: 2px solid #1a4a6e;
            background: white;
            color: #1a4a6e;
        }
        .footer-note {
            background: #ffffffcc;
            backdrop-filter: blur(12px);
            border-radius: 30px;
            padding: 15px;
            text-align: center;
            font-size: 0.8rem;
            margin-top: 15px;
        }
        @media (max-width: 650px) {
            .q-text { font-size: 0.85rem; }
            .option label { font-size: 0.75rem; }
            .title-section h1 { font-size: 1.2rem; }
            .profile-image { width: 55px; height: 55px; }
            .tab-btn { padding: 6px 16px; font-size: 0.75rem; }
            .fill-input { width: calc(100% - 44px); }
        }
    </style>
</head>
<body>
<div class="container">
    <div class="exam-header">
        <div class="header-top">
            <div class="title-section">
                <h1>🧪 بنك امتحانات الفورامينفرا – جامعة سوهاج</h1>
                <p>الفرقة الثانية – العلوم البيولوجية والجيولوجية</p>
            </div>
            <div class="profile-image">
                <img src="https://i.postimg.cc/pV9jC9J9/Screenshot-20260512-173337.jpg" alt="شعار الاختبار">
            </div>
        </div>
        <div class="credit-name">
            🧠 تم الإنشاء بواسطة: <span>Ahmed Hassan (أحمد حسن)</span> | تصحيح فوري مع التعليل
        </div>
        
        <div class="tabs-container" id="tabsContainer">
            <button class="tab-btn" data-exam="exam1">📘 امتحان الفورامينفرا (صح/خطأ)</button>
            <button class="tab-btn" data-exam="exam2">📙 أسئلة الشيت (اختياري + صح/خطأ)</button>
            <button class="tab-btn active" data-exam="exam3">📗 الامتحان السابق (اختياري + صح/خطأ + أكمل)</button>
        </div>
        
        <div class="progress-stats">
            <span>📌 تم الإجابة: <span id="answeredCount">0</span></span>
            <span>✅ الصحيحة: <span id="correctCount">0</span></span>
            <span>❌ الخاطئة: <span id="wrongCount">0</span></span>
            <span>📖 الامتحان: <span id="examLabel">الامتحان السابق</span></span>
        </div>
    </div>

    <div id="questionsContainer"></div>

    <div class="action-bar">
        <button class="btn btn-primary" id="resetBtn">🔄 إعادة تعيين الإجابات</button>
        <button class="btn btn-outline" id="scrollTopBtn">⬆️ العودة للأعلى</button>
    </div>
    <div class="footer-note">
        💡 اختر الإجابة الصحيحة - سيظهر لك التصحيح مع التعليل من الورقة الامتحانية.
    </div>
</div>

<script>
    // ============================================================
    // الامتحان الأول: الفورامينفرا (20 سؤال صح/خطأ)
    // الامتحان الثاني: أسئلة الشيت (10 اختياري + 5 صح/خطأ)
    // الامتحان الثالث: الامتحان السابق (25 اختياري + 25 صح/خطأ + 8 أكمل)
    // جميع الأسئلة مستخلصة من الملف الأصلي - بدون إضافات
    // ============================================================

    // -------------------- الامتحان الأول: 20 سؤال صح/خطأ --------------------
    const exam1Questions = [
        { type: "tf", text: "تتبع الفورامينفرا دورا هاما في النظام البحري، ولهما تطبيقات في علم الطبقات واستكشاف البترول.", correct: "صح", explanation: "الورقة: العبارة رقم 6 - صحيحة" },
        { type: "tf", text: "وجود تنوع في انواع الصداف الفورامينفرا يكون دليل على أن المنطقة كانت فقيرة بمصادر الغذاء.", correct: "خطأ", explanation: "الورقة: العبارة رقم 7 - 'كانت غنية بمصادر الغذاء' وليس فقيرة" },
        { type: "tf", text: "القيعان الرملية والطينية تكون غنية بالعناصر الغذائية اللازمة لمعيشة الفورامينفرا عليها.", correct: "خطأ", explanation: "الورقة: العبارة رقم 8 - 'القيعان الرملية والطينية تكون فقيره في وجود العناصر الغذائية'" },
        { type: "tf", text: "تحتوي المسامات الأكبر في الرمال والحصى على مغذيات أكثر وبالتالي تنوع في الفورامينفرا.", correct: "صح", explanation: "الورقة: العبارة رقم 9 - صحيحة" },
        { type: "tf", text: "النطاق الضوئي يكون عميقاً في المناطق الاستوائية وضحلاً تجاه القطبين.", correct: "خطأ", explanation: "الورقة: العبارة رقم 10 - 'يكون ضحلاً في المناطق الاستوائية ويزداد عمقه تجاه قطبي الكرة الأرضية'" },
        { type: "tf", text: "يتكيف كل نوع من أنواع الفورامينفرا مع مدى معين من درجات الحرارة ودرجات الملوحة.", correct: "صح", explanation: "الورقة: العبارة رقم 11 - صحيحة" },
        { type: "tf", text: "تزداد كثافة الفورامينفرا الطافية Planktonic Foraminifera ناحية المناطق القطبية.", correct: "خطأ", explanation: "الورقة: العبارة رقم 16 - 'تزداد كثافة الفورامينفرا الطاقيه ناحية المناطق الاستوائية'" },
        { type: "tf", text: "وجود مصراعي الدرقة في الأوستراكودا متصلان ببعضهما دليل على معدل ترسيب مرتفع.", correct: "خطأ", explanation: "الورقة: العبارة رقم 17 - 'دليل علي معدل ترسيب منخفض'" },
        { type: "tf", text: "من الفورامينفرا الكبيرة والمرشدة التي سادت في زمن الكربوني والبرمي Family: Fusulinidae.", correct: "صح", explanation: "الورقة: العبارة رقم 18 - صحيحة" },
        { type: "tf", text: "تتميز اصداف الفورامينفرا ذات اللف المخروطي العالي بان الفتحة تكون سرية.", correct: "صح", explanation: "الورقة: العبارة رقم 20 - صحيحة" },
        { type: "tf", text: "تعيش الأوستراكودا متكافئة مع الطحالب البحرية Marine algae.", correct: "صح", explanation: "الورقة: العبارة رقم 21 - صحيحة" },
        { type: "tf", text: "يعتبر حيوان الفورامينفرا من الكائنات البحرية ذاتية التغذية Autotrophic.", correct: "خطأ", explanation: "الورقة: العبارة رقم 22 - 'عضوية التغذية Heterotrophic'" },
        { type: "tf", text: "تسود الفورامينفرا ذات الجدار الرملي Arenaceous في الأعماق البحرية وتقل في المناطق الضحلة.", correct: "صح", explanation: "الورقة: العبارة رقم 25 - صحيحة" },
        { type: "tf", text: "سجلت اقصي زيادة في اعداد وانواع الفورامينفرا الطاقيه خلال العصر الحديث.", correct: "خطأ", explanation: "الورقة: العبارة رقم 26 - 'خلال الطباشيري العلوي'" },
        { type: "tf", text: "نشأ الجدار الجيري الزجاجي قبل الجدار الجيري الصيني (الخزفي).", correct: "صح", explanation: "الورقة: العبارة رقم 13 - صحيحة" },
        { type: "tf", text: "يسمى الجزء الصلب الذي يحفظ حيوان الأوستراكودا باسم الدرقة Carapace.", correct: "صح", explanation: "الورقة: العبارة رقم 14 - صحيحة" },
        { type: "tf", text: "يرتبط مصراعي الأوستراكودا بواسطة المفضلة والعطلات Hinge & muscles.", correct: "صح", explanation: "الورقة: العبارة رقم 15 - صحيحة" },
        { type: "tf", text: "في القطاع الرقيق لدرقة الأوستراكودا تظهر أنها مكونة من طبقتين فقط.", correct: "خطأ", explanation: "الورقة: العبارة رقم 19 - 'مكونه من ثلاث طبقات'" },
        { type: "tf", text: "تتكيف الفورامينفرا الطاقيه مع مستويات المياه في المحيطات ذات درجات الحرارة والكثافات المختلفة.", correct: "صح", explanation: "الورقة: العبارة رقم 12 - صحيحة" },
        { type: "tf", text: "تتأثر أنواع الفورامينفرا بدرجة الملوحة (Salinity).", correct: "صح", explanation: "الورقة: العبارتان 23 و 24 - صحيح" }
    ];

    // -------------------- الامتحان الثاني: أسئلة الشيت --------------------
    const exam2Mcq = [
        { type: "mcq", text: "تكون الجدار الجيري في أصداف الفورامينفرا من معدن:", options: ["أ) الكالسيد", "ب) السيليكا", "ج) الكيتين", "د) الفوسفات"], correct: "أ", explanation: "الورقة: 'تكون الجدار الجيري في أصدقاء الفورامينفرا من معدن (أ - الكلسيد)'" },
        { type: "mcq", text: "تكرار أعداد الفورامينفرا القاعدية فوق القيمين البصرية:", options: ["أ) الغرينية", "ب) الرملية", "ج) الطينية", "د) الصخرية"], correct: "أ", explanation: "الورقة: 'تكرار أعداد الفورامينفرا القاعدية فوق القيمين البصرية (أ - الغرينية)'" },
        { type: "mcq", text: "توجد أصداف الفورامينفرا في المحسوس السوداني:", options: ["أ) الكلوروفلوريدات", "ب) الكربونات", "ج) السيليكات", "د) الأكسيدات"], correct: "أ", explanation: "الورقة: 'توجد أصدقاء الفورامينفرا في المحسوس السوداني (أ - الكلوروفلوريدات)'" },
        { type: "mcq", text: "تأخذ بعض أصداف الفورامينفرا ذات عديدة الحجرات الشكل:", options: ["أ) الكربون", "ب) الحلزوني", "ج) المخروطي", "د) القرصي"], correct: "أ", explanation: "الورقة: 'تأخذ بعض أصدقاء الفورامينفرا ذات عديدة الحجرات الشكل (أ - الكربون)'" },
        { type: "mcq", text: "يكون مكان النتيجة في الأصداف ذات اللغات المطروحة على شكل Paleoecology:", options: ["أ) سريع", "ب) بطيء", "ج) دائري", "د) بيضاوي"], correct: "أ", explanation: "الورقة: 'يكون مكان النتيجة في الأصدقاء ذات اللغات المطروحة على شكل Paleoecology (أ - سريع)'" },
        { type: "mcq", text: "يظهر الأقدام الكاذبة في الفورامينفرا وظيفتها:", options: ["أ) الحركة والتثبيت", "ب) التنفس", "ج) الهضم", "د) الإخراج"], correct: "أ", explanation: "الورقة: 'يظهر الأقدام الكاذبة في الفورامينفرا هي (أ - الحركة والتثبيت)'" },
        { type: "mcq", text: "تتصل حجرة الفورامينفرا بالتي سبقتها في التكوين بما يعرف بـ:", options: ["أ) الناقص", "ب) المسام", "ج) الثقب", "د) الحاجز"], correct: "أ", explanation: "الورقة: 'تتصل حجرة الفورامينفرا بالتي سبقتها في التكوين بما يسعى به (أ - الناقص)'" },
        { type: "mcq", text: "يوجد الجانب البيئي في الأصداف ذات التربة:", options: ["أ) الخضراء", "ب) الرملية", "ج) الطينية", "د) الصخرية"], correct: "أ", explanation: "الورقة: 'يوجد الجانب البيئي في الأصدقاء ذات التربة (أ - الخضراء)'" },
        { type: "mcq", text: "تشمل المخاطر الإيجابية التي يتعرض لها حيوان الفورامينفرا:", options: ["أ) تغير درجة الحرارة", "ب) نقص الغذاء", "ج) زيادة الأكسجين", "د) قلة الضوء"], correct: "أ", explanation: "الورقة: 'تشمل المخاطر الإيجابية التي يتعرض لها الحيوان الفورامينفرا (أ - تغير درجة الحرارة)'" },
        { type: "mcq", text: "تسهل المشاكل البيئية التي يتعرض لها حيوان الفورامينفرا:", options: ["أ) تغير درجة حرارة", "ب) الملوحة", "ج) الضغط", "د) التيارات"], correct: "أ", explanation: "الورقة: 'تسهل المشاكل البيئية التي يتعرض لها الحيوان الفورامينفرا (أ - تغير درجة حرارة)'" }
    ];

    const exam2Tf = [
        { type: "tf", text: "تؤدي النقلات والوقوف وظيفتها داخل وخارج صدفة الفورامينفرا في تنظيم دخول وخروج السوائل.", correct: "صح", explanation: "الورقة: 'تؤدي النقلات والوقوف وظيفتها داخل وخارج صدفة الفورامينفرا في تنظيم دخول و خروج السوائل' - صحيحة" },
        { type: "tf", text: "تحتوي فراغات القيمين الرملية، الحصوية على مغذيات قليلة وتكون أصداف الفورامينفرا ذات شكل مغزلي أو عدسي الشكل.", correct: "صح", explanation: "الورقة: صحيحة" },
        { type: "tf", text: "يزداد عمق النطاق الضوئي في المناطق القطبية ويقل في المناطق الاستوائية.", correct: "صح", explanation: "الورقة: صحيحة" },
        { type: "tf", text: "يسمى الجانب الذي تظهر فيه حجرات اللغة الأخيرة في الأصداف ذات اللغات المطروحة بالجانب الظهري.", correct: "صح", explanation: "الورقة: صحيحة" },
        { type: "tf", text: "تتميز أنواع الفورامينفرا التي تعيش فوق القيمين الصلبة بأن أصدافها تكون قرصية أو حلقية أو مروحية.", correct: "صح", explanation: "الورقة: صحيحة" }
    ];

    const exam2Questions = [...exam2Mcq, ...exam2Tf];

    // -------------------- الامتحان الثالث: الامتحان السابق (25 اختياري + 25 صح/خطأ + 8 أكمل) --------------------
    // 25 سؤال اختياري من العبارات (6-26)
    const exam3Mcq = [
        { type: "mcq", text: "تلعب الفورامنيفرا دورا هاما في النظام البحري ولها تطبيقات في:", options: ["أ) الزراعة", "ب) علم الطبقات واستكشاف البترول", "ج) الصناعة الغذائية", "د) الطب"], correct: "ب", explanation: "الورقة: العبارة 6 - 'علم الطبقات، استكشاف البترول'" },
        { type: "mcq", text: "وجود تنوع في انواع اصداف الفورامنيفرا يدل على أن المنطقة كانت:", options: ["أ) فقيرة بالغذاء", "ب) غنية بمصادر الغذاء", "ج) عميقة", "د) ضحلة"], correct: "ب", explanation: "الورقة: العبارة 7 - 'غنية بمصادر الغذاء آنذاك'" },
        { type: "mcq", text: "القيعان الرملية والطينية تكون في وجود العناصر الغذائية:", options: ["أ) غنية", "ب) فقيرة", "ج) متوسطة", "د) غير مؤثرة"], correct: "ب", explanation: "الورقة: العبارة 8 - 'فقيره في وجود العناصر الغذائية'" },
        { type: "mcq", text: "تحتوي المسامات الأكبر في الرمال والحصى على:", options: ["أ) مغذيات أقل", "ب) مغذيات أكثر", "ج) أملاح أكثر", "د) طين أكثر"], correct: "ب", explanation: "الورقة: العبارة 9 - 'على مغذيات اكثر'" },
        { type: "mcq", text: "النطاق الضوئي يكون في المناطق الاستوائية:", options: ["أ) عميقاً", "ب) ضحلاً", "ج) معدوماً", "د) متغيراً"], correct: "ب", explanation: "الورقة: العبارة 10 - 'يكون ضحلا في المناطق الاستوائية'" },
        { type: "mcq", text: "النطاق الضوئي يزداد عمقه تجاه:", options: ["أ) خط الإستواء", "ب) قطبي الكرة الأرضية", "ج) خطوط الطول", "د) خطوط العرض"], correct: "ب", explanation: "الورقة: العبارة 10 - 'يزداد عمقه تجاه قطبي الكره الأرضية'" },
        { type: "mcq", text: "يتكيف كل نوع من انواع الفورامنيفرا مع مدى معين من:", options: ["أ) الضغط فقط", "ب) الحرارة والملوحة", "ج) التيارات فقط", "د) العمق فقط"], correct: "ب", explanation: "الورقة: العبارة 11 - 'درجات الحرارة، درجات الملوحة'" },
        { type: "mcq", text: "نشأ الجدار الجيري الزجاجي قبل:", options: ["أ) الجدار الرملي", "ب) الجدار الجيري الصيني (الخزفي)", "ج) الجدار السيليسي", "د) الجدار العضوي"], correct: "ب", explanation: "الورقة: العبارة 13 - 'قبل الجدار الجيري الصيني (الخزفي)'" },
        { type: "mcq", text: "الجزء الصلب الذي يحفظ حيوان الأوستراكودا يسمى:", options: ["أ) الدرقة Carapace", "ب) الصدفة", "ج) القوقعة", "د) الهيكل الخارجي"], correct: "أ", explanation: "الورقة: العبارة 14 - 'الدرقة Carapace'" },
        { type: "mcq", text: "يرتبط مصراعي الأوستراكودا بواسطة:", options: ["أ) المفضلة والعطلات Hinge & muscles", "ب) الأربطة", "ج) العضلات فقط", "د) المفاصل"], correct: "أ", explanation: "الورقة: العبارة 15 - 'المفضلة والعطلات Hinge & muscles'" },
        { type: "mcq", text: "تزداد كثافة الفورامنيفرا الطاقيه Planktonic Foraminifera ناحية:", options: ["أ) المناطق القطبية", "ب) المناطق الاستوائية", "ج) الأعماق", "د) الشواطئ"], correct: "ب", explanation: "الورقة: العبارة 16 - 'ناحية المناطق الاستوائية'" },
        { type: "mcq", text: "وجود مصراعي الدرقة في الأوستراكودا متصلان ببعضهما يدل على:", options: ["أ) معدل ترسيب مرتفع", "ب) معدل ترسيب منخفض", "ج) بيئة عميقة", "د) بيئة ضحلة"], correct: "ب", explanation: "الورقة: العبارة 17 - 'دليل علي معدل ترسيب منخفض'" },
        { type: "mcq", text: "من الفورامنيفرا الكبيرة والمرشدة التي سادت في زمن الكربوني والبرمي:", options: ["أ) Globigerinidae", "ب) Fusulinidae", "ج) Miliolidae", "د) Rotaliidae"], correct: "ب", explanation: "الورقة: العبارة 18 - 'Family: Fusulinidae'" },
        { type: "mcq", text: "في القطاع الرقيق لدرقة الأوستراكودا تظهر أنها مكونة من:", options: ["أ) طبقتين", "ب) ثلاث طبقات", "ج) أربع طبقات", "د) طبقة واحدة"], correct: "ب", explanation: "الورقة: العبارة 19 - 'ثلاث طبقات'" },
        { type: "mcq", text: "تتميز اصداف الفورامنيفرا ذات اللف المخروطي العالي بأن الفتحة تكون:", options: ["أ) سرية", "ب) مركزية", "ج) هامشية", "د) قاعدية"], correct: "أ", explanation: "الورقة: العبارة 20 - 'الفتحة تكون سري'" },
        { type: "mcq", text: "تعيش الأوستراكودا متكافئة مع:", options: ["أ) الطحالب البحرية Marine algae", "ب) الشعاب المرجانية", "ج) الأسماك", "د) القشريات"], correct: "أ", explanation: "الورقة: العبارة 21 - 'الطحالب البحرية Marine algae'" },
        { type: "mcq", text: "يعتبر حيوان الفورامنيفرا من الكائنات البحرية:", options: ["أ) ذاتية التغذية Autotrophic", "ب) عضوية التغذية Heterotrophic", "ج) رممية", "د) طفيلية"], correct: "ب", explanation: "الورقة: العبارة 22 - 'عضويه التغذية Heterotrophic'" },
        { type: "mcq", text: "تسود الفورامنيفرا ذات الجدار الرملي Arenaceous في:", options: ["أ) المناطق الضحلة", "ب) الأعماق البحرية", "ج) مصبات الأنهار", "د) البحيرات"], correct: "ب", explanation: "الورقة: العبارة 25 - 'تسود في الأعماق البحرية'" },
        { type: "mcq", text: "تقل الفورامنيفرا ذات الجدار الرملي Arenaceous في:", options: ["أ) الأعماق البحرية", "ب) المناطق الضحلة", "ج) المحيطات المفتوحة", "د) الخنادق"], correct: "ب", explanation: "الورقة: العبارة 25 - 'تقل في المناطق الضحلة'" },
        { type: "mcq", text: "سجلت اقصي زيادة في اعداد وانواع الفورامنيفرا الطاقيه خلال:", options: ["أ) العصر الحديث", "ب) الطباشيري العلوي", "ج) الجوراسي", "د) الديفوني"], correct: "ب", explanation: "الورقة: العبارة 26 - 'خلال الطباشيري العلوي'" },
        { type: "mcq", text: "تتكيف الفورامنيفرا الطاقيه مع مستويات المياه في المحيطات ذات:", options: ["أ) ملوحة ثابتة", "ب) درجات حرارة وكثافات مختلفة", "ج) تيارات قوية", "د) ضغط مرتفع"], correct: "ب", explanation: "الورقة: العبارة 12 - 'درجات الحرارة والكثافات المختلفة'" },
        { type: "mcq", text: "تتأثر أنواع الفورامنيفرا بعامل:", options: ["أ) الرياح", "ب) الملوحة Salinity", "ج) المد والجزر", "د) الأمواج"], correct: "ب", explanation: "الورقة: العبارتان 23-24 - 'تتأثر انواع Salinity'" },
        { type: "mcq", text: "الجدار الجيري الزجاجي يسمى:", options: ["أ) Calcareous wall", "ب) Siliceous wall", "ج) Organic wall", "د) Agglutinated wall"], correct: "أ", explanation: "الورقة: العبارة 13 - 'الجدار الجيري الزجاجي Calcareous wall'" },
        { type: "mcq", text: "الأوستراكودا هي حيوانات:", options: ["أ) بحرية", "ب) برية", "ج) مياه عذبة فقط", "د) طفيلية"], correct: "أ", explanation: "الورقة: العبارات 14 و15 و17 و19 و21 تتحدث عن الأوستراكودا ككائن بحري" },
        { type: "mcq", text: "الفورامنيفرا الكبيرة والمرشدة ساعدت في تحديد عمر طبقات:", options: ["أ) عصر دهر الحياة القديمة", "ب) عصر دهر الحياة الحديثة", "ج) الزمن الكربوني والبرمي", "د) عصر دهر الحياة الوسطى"], correct: "ج", explanation: "الورقة: العبارة 18 - 'زمن الكربوني والبرمي'" }
    ];

    // 25 سؤال صح/خطأ من العبارات (نفسها ولكن بصيغة مختلفة)
    const exam3Tf = [
        { type: "tf", text: "الفورامنيفرا تلعب دوراً هاماً في النظام البحري ولها تطبيقات في علم الطبقات واستكشاف البترول.", correct: "صح", explanation: "الورقة: العبارة 6 - صحيحة" },
        { type: "tf", text: "تنوع أصداف الفورامنيفرا يدل على فقر المنطقة بمصادر الغذاء.", correct: "خطأ", explanation: "الورقة: العبارة 7 - يدل على الغنى بمصادر الغذاء" },
        { type: "tf", text: "القيعان الرملية والطينية غنية بالعناصر الغذائية للفورامنيفرا.", correct: "خطأ", explanation: "الورقة: العبارة 8 - تكون فقيرة" },
        { type: "tf", text: "المسامات الأكبر في الرمال والحصى تحتوي على مغذيات أقل.", correct: "خطأ", explanation: "الورقة: العبارة 9 - تحتوي على مغذيات أكثر" },
        { type: "tf", text: "النطاق الضوئي يكون عميقاً في المناطق الاستوائية.", correct: "خطأ", explanation: "الورقة: العبارة 10 - يكون ضحلاً في المناطق الاستوائية" },
        { type: "tf", text: "عمق النطاق الضوئي يزداد تجاه قطبي الكرة الأرضية.", correct: "صح", explanation: "الورقة: العبارة 10 - يزداد عمقه تجاه قطبي الكرة الأرضية" },
        { type: "tf", text: "الفورامنيفرا لا تتأثر بدرجات الحرارة.", correct: "خطأ", explanation: "الورقة: العبارة 11 - تتكيف مع مدى معين من درجات الحرارة" },
        { type: "tf", text: "الجدار الجيري الزجاجي نشأ بعد الجدار الجيري الصيني.", correct: "خطأ", explanation: "الورقة: العبارة 13 - نشأ قبل الجدار الجيري الصيني" },
        { type: "tf", text: "الدرقة Carapace هي الجزء الصلب الذي يحفظ الأوستراكودا.", correct: "صح", explanation: "الورقة: العبارة 14 - صحيحة" },
        { type: "tf", text: "مصراعا الأوستراكودا غير مرتبطين ببعضهما.", correct: "خطأ", explanation: "الورقة: العبارة 15 - يرتبطان بواسطة المفضلة والعطلات" },
        { type: "tf", text: "كثافة الفورامنيفرا الطافية تزداد في المناطق القطبية.", correct: "خطأ", explanation: "الورقة: العبارة 16 - تزداد في المناطق الاستوائية" },
        { type: "tf", text: "اتصال مصراعي الدرقة يدل على ارتفاع معدل الترسيب.", correct: "خطأ", explanation: "الورقة: العبارة 17 - يدل على معدل ترسيب منخفض" },
        { type: "tf", text: "الفورامنيفرا الكبيرة والمرشدة هي من عائلة Fusulinidae.", correct: "صح", explanation: "الورقة: العبارة 18 - صحيحة" },
        { type: "tf", text: "درقة الأوستراكودا مكونة من طبقتين.", correct: "خطأ", explanation: "الورقة: العبارة 19 - مكونة من ثلاث طبقات" },
        { type: "tf", text: "الأصداف ذات اللف المخروطي العالي فتحتها سرية.", correct: "صح", explanation: "الورقة: العبارة 20 - صحيحة" },
        { type: "tf", text: "الأوستراكودا تعيش متكافئة مع الطحالب البحرية.", correct: "صح", explanation: "الورقة: العبارة 21 - صحيحة" },
        { type: "tf", text: "الفورامنيفرا من الكائنات ذاتية التغذية.", correct: "خطأ", explanation: "الورقة: العبارة 22 - عضوية التغذية" },
        { type: "tf", text: "الجدار الرملي يسود في الأعماق البحرية.", correct: "صح", explanation: "الورقة: العبارة 25 - تسود في الأعماق البحرية" },
        { type: "tf", text: "الفورامنيفرا الرملية تقل في المناطق الضحلة.", correct: "صح", explanation: "الورقة: العبارة 25 - تقل في المناطق الضحلة" },
        { type: "tf", text: "أقصى زيادة للفورامنيفرا الطافية كانت في العصر الحديث.", correct: "خطأ", explanation: "الورقة: العبارة 26 - خلال الطباشيري العلوي" },
        { type: "tf", text: "الفورامنيفرا الطاقيه تتكيف مع حرارة وكثافة مختلفة.", correct: "صح", explanation: "الورقة: العبارة 12 - صحيحة" },
        { type: "tf", text: "تتأثر الفورامنيفرا بدرجة الملوحة Salinity.", correct: "صح", explanation: "الورقة: العبارات 23-24 - صحيحة" },
        { type: "tf", text: "الأوستراكودا من القشريات البحرية.", correct: "صح", explanation: "من خلال سياق الورقة - صحيحة" },
        { type: "tf", text: "الفورامنيفرا الكبيرة والمرشدة عاشت في الزمن الطباشيري فقط.", correct: "خطأ", explanation: "الورقة: العبارة 18 - سادت في زمن الكربوني والبرمي" },
        { type: "tf", text: "القطاع الرقيق لدرقة الأوستراكودا يظهر ثلاث طبقات.", correct: "صح", explanation: "الورقة: العبارة 19 - صحيحة" }
    ];

    // 8 أسئلة أكمل
    const exam3Fill = [
        { type: "fill", text: "الفورامنيفرا تلعب دورا هاما في النظام البحري ولها تطبيقات في علم الطبقات و...............", correctAnswer: "استكشاف البترول", explanation: "الورقة: العبارة 6 - استكشاف البترول" },
        { type: "fill", text: "وجود تنوع في انواع اصداف الفورامنيفرا يكون دليل علي ان المنطقة كانت غنية بمصادر ...............", correctAnswer: "الغذاء", explanation: "الورقة: العبارة 7 - مصادر الغذاء" },
        { type: "fill", text: "النطاق الضوئي يزداد عمقه تجاه قطبي الكرة ...............", correctAnswer: "الأرضية", explanation: "الورقة: العبارة 10 - قطبي الكره الأرضية" },
        { type: "fill", text: "يتكيف كل نوع من انواع الفورامنيفرا مع مدى معين من درجات الحرارة ودرجات ...............", correctAnswer: "الملوحة", explanation: "الورقة: العبارة 11 - درجات الملوحة" },
        { type: "fill", text: "يسمى الجزء الصلب الذي يحفظ حيوان الأوستراكودا باسم ............... Carapace", correctAnswer: "الدرقة", explanation: "الورقة: العبارة 14 - الدرقة Carapace" },
        { type: "fill", text: "تزداد كثافة الفورامنيفرا الطاقيه ناحية المناطق ...............", correctAnswer: "الاستوائية", explanation: "الورقة: العبارة 16 - المناطق الاستوائية" },
        { type: "fill", text: "سجلت اقصي زيادة في اعداد وانواع الفورامنيفرا الطاقيه خلال الطباشيري ...............", correctAnswer: "العلوي", explanation: "الورقة: العبارة 26 - الطباشيري العلوي" },
        { type: "fill", text: "تسود الفورامنيفرا ذات الجدار الرملي Arenaceous في ............... البحرية", correctAnswer: "الأعماق", explanation: "الورقة: العبارة 25 - الأعماق البحرية" }
    ];

    const exam3Questions = [...exam3Mcq, ...exam3Tf, ...exam3Fill];

    const banks = {
        exam1: exam1Questions,
        exam2: exam2Questions,
        exam3: exam3Questions
    };

    let currentExam = "exam3";
    let userAnswers = new Array(banks[currentExam].length).fill(null);
    let answerStatus = new Array(banks[currentExam].length).fill(null);
    let fillInputValues = new Array(banks[currentExam].length).fill("");

    function saveToLocal() {
        localStorage.setItem('foram_final_current', currentExam);
        localStorage.setItem('foram_final_answers', JSON.stringify(userAnswers));
        localStorage.setItem('foram_final_status', JSON.stringify(answerStatus));
        localStorage.setItem('foram_final_fill', JSON.stringify(fillInputValues));
    }

    function loadFromLocal() {
        const savedExam = localStorage.getItem('foram_final_current');
        if(savedExam && banks[savedExam]) currentExam = savedExam;
        const savedAnswers = localStorage.getItem('foram_final_answers');
        const savedStatus = localStorage.getItem('foram_final_status');
        const savedFill = localStorage.getItem('foram_final_fill');
        if(savedAnswers) userAnswers = JSON.parse(savedAnswers);
        if(savedStatus) answerStatus = JSON.parse(savedStatus);
        if(savedFill) fillInputValues = JSON.parse(savedFill);
        else fillInputValues = new Array(banks[currentExam].length).fill("");
        if(userAnswers.length !== banks[currentExam].length) {
            userAnswers = new Array(banks[currentExam].length).fill(null);
            answerStatus = new Array(banks[currentExam].length).fill(null);
            fillInputValues = new Array(banks[currentExam].length).fill("");
        }
        updateActiveTab();
        updateExamLabel();
        renderAllQuestions();
        updateStats();
    }

    function updateActiveTab() {
        document.querySelectorAll('.tab-btn').forEach(btn => {
            if(btn.dataset.exam === currentExam) btn.classList.add('active');
            else btn.classList.remove('active');
        });
    }

    function updateExamLabel() {
        const labelSpan = document.getElementById('examLabel');
        if(currentExam === 'exam1') labelSpan.innerText = 'امتحان الفورامينفرا';
        else if(currentExam === 'exam2') labelSpan.innerText = 'أسئلة الشيت';
        else labelSpan.innerText = 'الامتحان السابق';
    }

    function updateStats() {
        let answered = 0, correct = 0, wrong = 0;
        for(let i=0; i<userAnswers.length; i++) {
            if(userAnswers[i] !== null) {
                answered++;
                if(answerStatus[i] === 'correct') correct++;
                else if(answerStatus[i] === 'wrong') wrong++;
            }
        }
        document.getElementById('answeredCount').innerText = answered;
        document.getElementById('correctCount').innerText = correct;
        document.getElementById('wrongCount').innerText = wrong;
    }

    function evaluateFill(idx, userText) {
        const q = banks[currentExam][idx];
        const normalizedUser = userText.trim().replace(/[\s\u060C\u061B\u061F]+$/, '').toLowerCase();
        const normalizedCorrect = q.correctAnswer.trim().toLowerCase();
        const isCorrect = (normalizedUser === normalizedCorrect);
        userAnswers[idx] = userText;
        answerStatus[idx] = isCorrect ? 'correct' : 'wrong';
        fillInputValues[idx] = userText;
        saveToLocal();
        updateStats();
        renderSingleQuestion(idx);
    }

    function evaluateAnswer(idx, selectedValue) {
        const q = banks[currentExam][idx];
        let isCorrect = false;
        if(q.type === 'mcq') {
            isCorrect = (selectedValue === q.correct);
        } else if(q.type === 'tf') {
            isCorrect = (selectedValue === q.correct);
        } else {
            isCorrect = (selectedValue === q.correctAnswer);
        }
        userAnswers[idx] = selectedValue;
        answerStatus[idx] = isCorrect ? 'correct' : 'wrong';
        saveToLocal();
        updateStats();
        renderSingleQuestion(idx);
    }

    function renderSingleQuestion(idx) {
        const q = banks[currentExam][idx];
        const container = document.getElementById(`q-${idx}`);
        if(!container) return;
        const selected = userAnswers[idx];
        const status = answerStatus[idx];

        let optionsHtml = '';
        let contentHtml = '';

        if(q.type === 'mcq') {
            optionsHtml = q.options.map(opt => {
                const optLetter = opt.charAt(0);
                const isChecked = (selected === optLetter);
                return `<div class="option" data-choice="${optLetter}">
                            <input type="radio" name="q${idx}" id="q${idx}_${optLetter}" value="${optLetter}" ${isChecked ? 'checked' : ''}>
                            <label for="q${idx}_${optLetter}">${opt}</label>
                        </div>`;
            }).join('');
            contentHtml = `<div class="options-area">${optionsHtml}</div>`;
        } else if(q.type === 'tf') {
            optionsHtml = `
                <div style="display:flex; flex-direction:row; gap:20px; flex-wrap:wrap;">
                    <div class="option-inline" data-choice="صح">
                        <input type="radio" name="q${idx}" id="q${idx}_true" value="صح" ${selected === 'صح' ? 'checked' : ''}>
                        <label for="q${idx}_true">أ) صح</label>
                    </div>
                    <div class="option-inline" data-choice="خطأ">
                        <input type="radio" name="q${idx}" id="q${idx}_false" value="خطأ" ${selected === 'خطأ' ? 'checked' : ''}>
                        <label for="q${idx}_false">ب) خطأ</label>
                    </div>
                </div>
            `;
            contentHtml = `<div class="options-area">${optionsHtml}</div>`;
        } else {
            const currentVal = fillInputValues[idx] || '';
            contentHtml = `<div>
                            <input type="text" id="fill-${idx}" class="fill-input" placeholder="اكتب الإجابة هنا..." value="${currentVal.replace(/"/g, '&quot;')}">
                            <button class="check-fill-btn" data-idx="${idx}">✔ تأكيد الإجابة</button>
                          </div>`;
        }

        let feedbackHtml = '';
        if(status === 'correct') {
            if(q.type === 'fill') {
                feedbackHtml = `<div class="feedback correct"><strong>✅ إجابة صحيحة</strong><br>📖 ${q.explanation}</div>`;
            } else {
                feedbackHtml = `<div class="feedback correct"><strong>✅ إجابة صحيحة</strong><br>📖 ${q.explanation}</div>`;
            }
        } else if(status === 'wrong') {
            if(q.type === 'mcq') {
                const correctText = q.options.find(opt => opt.startsWith(q.correct));
                feedbackHtml = `<div class="feedback wrong"><strong>❌ إجابة خاطئة. الإجابة الصحيحة: ${correctText}</strong><br>📖 ${q.explanation}</div>`;
            } else if(q.type === 'tf') {
                feedbackHtml = `<div class="feedback wrong"><strong>❌ إجابة خاطئة. الإجابة الصحيحة هي: ${q.correct}</strong><br>📖 ${q.explanation}</div>`;
            } else {
                feedbackHtml = `<div class="feedback wrong"><strong>❌ إجابة خاطئة. الإجابة الصحيحة هي: ${q.correctAnswer}</strong><br>📖 ${q.explanation}</div>`;
            }
        }

        const inner = `<div class="question-header">
                            <div class="q-num">${idx+1}</div>
                            <div class="q-text">${q.text}</div>
                        </div>
                        ${contentHtml}
                        <div>${feedbackHtml || ''}</div>`;
        container.innerHTML = inner;

        if(q.type !== 'fill') {
            const opts = container.querySelectorAll('.option, .option-inline');
            opts.forEach(div => {
                div.addEventListener('click', (e) => {
                    const radio = div.querySelector('input');
                    if(radio) radio.checked = true;
                    const choice = div.getAttribute('data-choice');
                    evaluateAnswer(idx, choice);
                });
                const radio = div.querySelector('input');
                if(radio) {
                    radio.addEventListener('change', (e) => {
                        if(radio.checked) evaluateAnswer(idx, radio.value);
                    });
                }
            });
        } else {
            const btn = container.querySelector('.check-fill-btn');
            if(btn) {
                btn.addEventListener('click', () => {
                    const input = container.querySelector(`#fill-${idx}`);
                    if(input) evaluateFill(idx, input.value);
                });
            }
        }
    }

    function renderAllQuestions() {
        const mainContainer = document.getElementById('questionsContainer');
        mainContainer.innerHTML = '';
        const questions = banks[currentExam];
        for(let i=0; i<questions.length; i++) {
            const cardDiv = document.createElement('div');
            cardDiv.className = 'question-card';
            cardDiv.id = `q-${i}`;
            mainContainer.appendChild(cardDiv);
            renderSingleQuestion(i);
        }
    }

    function switchExam(examId) {
        currentExam = examId;
        const newLen = banks[currentExam].length;
        userAnswers = new Array(newLen).fill(null);
        answerStatus = new Array(newLen).fill(null);
        fillInputValues = new Array(newLen).fill("");
        saveToLocal();
        updateActiveTab();
        updateExamLabel();
        renderAllQuestions();
        updateStats();
    }

    function resetCurrent() {
        const newLen = banks[currentExam].length;
        userAnswers = new Array(newLen).fill(null);
        answerStatus = new Array(newLen).fill(null);
        fillInputValues = new Array(newLen).fill("");
        saveToLocal();
        renderAllQuestions();
        updateStats();
    }

    document.querySelectorAll('.tab-btn').forEach(btn => {
        btn.addEventListener('click', () => switchExam(btn.dataset.exam));
    });
    document.getElementById('resetBtn').addEventListener('click', resetCurrent);
    document.getElementById('scrollTopBtn').addEventListener('click', () => window.scrollTo({top: 0, behavior: 'smooth'}));
    loadFromLocal();
</script>
</body>
</html>
