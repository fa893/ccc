<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>آلة حاسبة هندسية - مدرسة الأميرة إيمان بنت الحسين المهنية</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
            color: #333;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            background-color: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            width: 100%;
        }
        
        .school-name {
            color: #1a2a6c;
            font-size: 1.8rem;
            margin-bottom: 10px;
        }
        
        .calculator-title {
            color: #b21f1f;
            font-size: 2.2rem;
            margin-bottom: 15px;
        }
        
        .calculator-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            width: 100%;
        }
        
        .calculator-card {
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }
        
        .calculator-card:hover {
            transform: translateY(-5px);
        }
        
        .card-title {
            color: #1a2a6c;
            text-align: center;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #fdbb2d;
        }
        
        .input-group {
            margin-bottom: 15px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
            color: #333;
        }
        
        input, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        button {
            background: linear-gradient(to right, #1a2a6c, #b21f1f);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            width: 100%;
            margin-top: 10px;
            transition: all 0.3s ease;
        }
        
        button:hover {
            background: linear-gradient(to right, #b21f1f, #1a2a6c);
            transform: scale(1.02);
        }
        
        .result {
            margin-top: 15px;
            padding: 15px;
            background-color: #f8f9fa;
            border-radius: 5px;
            border-right: 4px solid #fdbb2d;
            font-weight: 600;
            text-align: center;
            display: none;
        }
        
        footer {
            margin-top: 30px;
            text-align: center;
            color: white;
            padding: 20px;
            width: 100%;
        }
        
        @media (max-width: 768px) {
            .calculator-grid {
                grid-template-columns: 1fr;
            }
            
            .school-name {
                font-size: 1.5rem;
            }
            
            .calculator-title {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1 class="school-name">مدرسة الأميرة إيمان بنت الحسين المهنية</h1>
            <h2 class="calculator-title">آلة حاسبة هندسية</h2>
        </header>
        
        <div class="calculator-grid">
            <!-- حاسبة مساحة الأشكال -->
            <div class="calculator-card">
                <h3 class="card-title">حاسبة مساحة الأشكال</h3>
                <div class="input-group">
                    <label for="shape">اختر الشكل:</label>
                    <select id="shape">
                        <option value="square">مربع</option>
                        <option value="rectangle">مستطيل</option>
                        <option value="triangle">مثلث</option>
                        <option value="circle">دائرة</option>
                    </select>
                </div>
                
                <div id="square-inputs" class="input-group">
                    <label for="side">طول الضلع:</label>
                    <input type="number" id="side" placeholder="أدخل طول الضلع">
                </div>
                
                <div id="rectangle-inputs" class="input-group" style="display: none;">
                    <label for="length">الطول:</label>
                    <input type="number" id="length" placeholder="أدخل الطول">
                    <label for="width">العرض:</label>
                    <input type="number" id="width" placeholder="أدخل العرض">
                </div>
                
                <div id="triangle-inputs" class="input-group" style="display: none;">
                    <label for="base">القاعدة:</label>
                    <input type="number" id="base" placeholder="أدخل طول القاعدة">
                    <label for="height">الارتفاع:</label>
                    <input type="number" id="height" placeholder="أدخل الارتفاع">
                </div>
                
                <div id="circle-inputs" class="input-group" style="display: none;">
                    <label for="radius">نصف القطر:</label>
                    <input type="number" id="radius" placeholder="أدخل نصف القطر">
                </div>
                
                <button id="calculate-area">احسب المساحة</button>
                <div id="area-result" class="result"></div>
            </div>
            
            <!-- حاسبة حجم الأشكال -->
            <div class="calculator-card">
                <h3 class="card-title">حاسبة حجم الأشكال</h3>
                <div class="input-group">
                    <label for="volume-shape">اختر الشكل:</label>
                    <select id="volume-shape">
                        <option value="cube">مكعب</option>
                        <option value="cuboid">متوازي مستطيلات</option>
                        <option value="cylinder">أسطوانة</option>
                        <option value="sphere">كرة</option>
                    </select>
                </div>
                
                <div id="cube-inputs" class="input-group">
                    <label for="cube-side">طول الضلع:</label>
                    <input type="number" id="cube-side" placeholder="أدخل طول الضلع">
                </div>
                
                <div id="cuboid-inputs" class="input-group" style="display: none;">
                    <label for="cuboid-length">الطول:</label>
                    <input type="number" id="cuboid-length" placeholder="أدخل الطول">
                    <label for="cuboid-width">العرض:</label>
                    <input type="number" id="cuboid-width" placeholder="أدخل العرض">
                    <label for="cuboid-height">الارتفاع:</label>
                    <input type="number" id="cuboid-height" placeholder="أدخل الارتفاع">
                </div>
                
                <div id="cylinder-inputs" class="input-group" style="display: none;">
                    <label for="cylinder-radius">نصف القطر:</label>
                    <input type="number" id="cylinder-radius" placeholder="أدخل نصف القطر">
                    <label for="cylinder-height">الارتفاع:</label>
                    <input type="number" id="cylinder-height" placeholder="أدخل الارتفاع">
                </div>
                
                <div id="sphere-inputs" class="input-group" style="display: none;">
                    <label for="sphere-radius">نصف القطر:</label>
                    <input type="number" id="sphere-radius" placeholder="أدخل نصف القطر">
                </div>
                
                <button id="calculate-volume">احسب الحجم</button>
                <div id="volume-result" class="result"></div>
            </div>
            
            <!-- حاسبة نظرية فيثاغورس -->
            <div class="calculator-card">
                <h3 class="card-title">نظرية فيثاغورس</h3>
                <div class="input-group">
                    <label for="pythagoras-side">ابحث عن:</label>
                    <select id="pythagoras-side">
                        <option value="hypotenuse">الوتر</option>
                        <option value="side">أحد الضلعين الآخرين</option>
                    </select>
                </div>
                
                <div class="input-group">
                    <label for="side-a">الضلع الأول (a):</label>
                    <input type="number" id="side-a" placeholder="أدخل طول الضلع الأول">
                </div>
                
                <div class="input-group">
                    <label for="side-b">الضلع الثاني (b):</label>
                    <input type="number" id="side-b" placeholder="أدخل طول الضلع الثاني">
                </div>
                
                <button id="calculate-pythagoras">احسب</button>
                <div id="pythagoras-result" class="result"></div>
            </div>
            
            <!-- حاسبة تحويل الوحدات -->
            <div class="calculator-card">
                <h3 class="card-title">تحويل الوحدات</h3>
                <div class="input-group">
                    <label for="conversion-type">نوع التحويل:</label>
                    <select id="conversion-type">
                        <option value="length">الطول</option>
                        <option value="area">المساحة</option>
                        <option value="volume">الحجم</option>
                    </select>
                </div>
                
                <div class="input-group">
                    <label for="from-unit">من:</label>
                    <select id="from-unit">
                        <option value="meter">متر</option>
                        <option value="centimeter">سنتيمتر</option>
                        <option value="kilometer">كيلومتر</option>
                    </select>
                </div>
                
                <div class="input-group">
                    <label for="to-unit">إلى:</label>
                    <select id="to-unit">
                        <option value="meter">متر</option>
                        <option value="centimeter">سنتيمتر</option>
                        <option value="kilometer">كيلومتر</option>
                    </select>
                </div>
                
                <div class="input-group">
                    <label for="conversion-value">القيمة:</label>
                    <input type="number" id="conversion-value" placeholder="أدخل القيمة">
                </div>
                
                <button id="calculate-conversion">تحويل</button>
                <div id="conversion-result" class="result"></div>
            </div>
        </div>
        
        <footer>
            <p>جميع الحقوق محفوظة &copy; 2023 - مدرسة الأميرة إيمان بنت الحسين المهنية</p>
        </footer>
    </div>

    <script>
        // التحكم في عرض حقول الإدخال بناءً على الشكل المختار
        document.getElementById('shape').addEventListener('change', function() {
            const shape = this.value;
            
            // إخفاء جميع حقول الإدخال
            document.getElementById('square-inputs').style.display = 'none';
            document.getElementById('rectangle-inputs').style.display = 'none';
            document.getElementById('triangle-inputs').style.display = 'none';
            document.getElementById('circle-inputs').style.display = 'none';
            
            // إظهار حقول الإدخال المناسبة
            document.getElementById(shape + '-inputs').style.display = 'block';
        });
        
        // التحكم في عرض حقول الإدخال لحاسبة الحجم
        document.getElementById('volume-shape').addEventListener('change', function() {
            const volumeShape = this.value;
            
            // إخفاء جميع حقول الإدخال
            document.getElementById('cube-inputs').style.display = 'none';
            document.getElementById('cuboid-inputs').style.display = 'none';
            document.getElementById('cylinder-inputs').style.display = 'none';
            document.getElementById('sphere-inputs').style.display = 'none';
            
            // إظهار حقول الإدخال المناسبة
            document.getElementById(volumeShape + '-inputs').style.display = 'block';
        });
        
        // حساب المساحة
        document.getElementById('calculate-area').addEventListener('click', function() {
            const shape = document.getElementById('shape').value;
            let area = 0;
            let resultText = '';
            
            switch(shape) {
                case 'square':
                    const side = parseFloat(document.getElementById('side').value);
                    if (!isNaN(side)) {
                        area = side * side;
                        resultText = `مساحة المربع = ${area.toFixed(2)}`;
                    }
                    break;
                    
                case 'rectangle':
                    const length = parseFloat(document.getElementById('length').value);
                    const width = parseFloat(document.getElementById('width').value);
                    if (!isNaN(length) && !isNaN(width)) {
                        area = length * width;
                        resultText = `مساحة المستطيل = ${area.toFixed(2)}`;
                    }
                    break;
                    
                case 'triangle':
                    const base = parseFloat(document.getElementById('base').value);
                    const height = parseFloat(document.getElementById('height').value);
                    if (!isNaN(base) && !isNaN(height)) {
                        area = 0.5 * base * height;
                        resultText = `مساحة المثلث = ${area.toFixed(2)}`;
                    }
                    break;
                    
                case 'circle':
                    const radius = parseFloat(document.getElementById('radius').value);
                    if (!isNaN(radius)) {
                        area = Math.PI * radius * radius;
                        resultText = `مساحة الدائرة = ${area.toFixed(2)}`;
                    }
                    break;
            }
            
            if (resultText) {
                document.getElementById('area-result').textContent = resultText;
                document.getElementById('area-result').style.display = 'block';
            } else {
                document.getElementById('area-result').textContent = 'يرجى إدخال قيم صحيحة';
                document.getElementById('area-result').style.display = 'block';
            }
        });
        
        // حساب الحجم
        document.getElementById('calculate-volume').addEventListener('click', function() {
            const volumeShape = document.getElementById('volume-shape').value;
            let volume = 0;
            let resultText = '';
            
            switch(volumeShape) {
                case 'cube':
                    const cubeSide = parseFloat(document.getElementById('cube-side').value);
                    if (!isNaN(cubeSide)) {
                        volume = Math.pow(cubeSide, 3);
                        resultText = `حجم المكعب = ${volume.toFixed(2)}`;
                    }
                    break;
                    
                case 'cuboid':
                    const cuboidLength = parseFloat(document.getElementById('cuboid-length').value);
                    const cuboidWidth = parseFloat(document.getElementById('cuboid-width').value);
                    const cuboidHeight = parseFloat(document.getElementById('cuboid-height').value);
                    if (!isNaN(cuboidLength) && !isNaN(cuboidWidth) && !isNaN(cuboidHeight)) {
                        volume = cuboidLength * cuboidWidth * cuboidHeight;
                        resultText = `حجم متوازي المستطيلات = ${volume.toFixed(2)}`;
                    }
                    break;
                    
                case 'cylinder':
                    const cylinderRadius = parseFloat(document.getElementById('cylinder-radius').value);
                    const cylinderHeight = parseFloat(document.getElementById('cylinder-height').value);
                    if (!isNaN(cylinderRadius) && !isNaN(cylinderHeight)) {
                        volume = Math.PI * Math.pow(cylinderRadius, 2) * cylinderHeight;
                        resultText = `حجم الأسطوانة = ${volume.toFixed(2)}`;
                    }
                    break;
                    
                case 'sphere':
                    const sphereRadius = parseFloat(document.getElementById('sphere-radius').value);
                    if (!isNaN(sphereRadius)) {
                        volume = (4/3) * Math.PI * Math.pow(sphereRadius, 3);
                        resultText = `حجم الكرة = ${volume.toFixed(2)}`;
                    }
                    break;
            }
            
            if (resultText) {
                document.getElementById('volume-result').textContent = resultText;
                document.getElementById('volume-result').style.display = 'block';
            } else {
                document.getElementById('volume-result').textContent = 'يرجى إدخال قيم صحيحة';
                document.getElementById('volume-result').style.display = 'block';
            }
        });
        
        // حساب نظرية فيثاغورس
        document.getElementById('calculate-pythagoras').addEventListener('click', function() {
            const sideType = document.getElementById('pythagoras-side').value;
            const sideA = parseFloat(document.getElementById('side-a').value);
            const sideB = parseFloat(document.getElementById('side-b').value);
            let result = 0;
            let resultText = '';
            
            if (sideType === 'hypotenuse') {
                if (!isNaN(sideA) && !isNaN(sideB)) {
                    result = Math.sqrt(Math.pow(sideA, 2) + Math.pow(sideB, 2));
                    resultText = `طول الوتر = ${result.toFixed(2)}`;
                }
            } else {
                if (!isNaN(sideA) && !isNaN(sideB)) {
                    if (sideA > sideB) {
                        result = Math.sqrt(Math.pow(sideA, 2) - Math.pow(sideB, 2));
                        resultText = `طول الضلع الآخر = ${result.toFixed(2)}`;
                    } else {
                        resultText = 'الضلع الأول يجب أن يكون أكبر من الضلع الثاني';
                    }
                }
            }
            
            if (resultText) {
                document.getElementById('pythagoras-result').textContent = resultText;
                document.getElementById('pythagoras-result').style.display = 'block';
            } else {
                document.getElementById('pythagoras-result').textContent = 'يرجى إدخال قيم صحيحة';
                document.getElementById('pythagoras-result').style.display = 'block';
            }
        });
        
        // تحويل الوحدات
        document.getElementById('calculate-conversion').addEventListener('click', function() {
            const conversionType = document.getElementById('conversion-type').value;
            const fromUnit = document.getElementById('from-unit').value;
            const toUnit = document.getElementById('to-unit').value;
            const value = parseFloat(document.getElementById('conversion-value').value);
            
            if (isNaN(value)) {
                document.getElementById('conversion-result').textContent = 'يرجى إدخال قيمة صحيحة';
                document.getElementById('conversion-result').style.display = 'block';
                return;
            }
            
            let result = 0;
            let resultText = '';
            
            // عوامل تحويل الطول
            const lengthFactors = {
                meter: 1,
                centimeter: 100,
                kilometer: 0.001
            };
            
            // عوامل تحويل المساحة
            const areaFactors = {
                meter: 1,
                centimeter: 10000,
                kilometer: 0.000001
            };
            
            // عوامل تحويل الحجم
            const volumeFactors = {
                meter: 1,
                centimeter: 1000000,
                kilometer: 0.000000001
            };
            
            let factors;
            switch(conversionType) {
                case 'length':
                    factors = lengthFactors;
                    break;
                case 'area':
                    factors = areaFactors;
                    break;
                case 'volume':
                    factors = volumeFactors;
                    break;
            }
            
            // التحويل إلى المتر أولاً ثم إلى الوحدة المطلوبة
            const valueInMeters = value / factors[fromUnit];
            result = valueInMeters * factors[toUnit];
            
            resultText = `${value} ${fromUnit} = ${result.toFixed(6)} ${toUnit}`;
            
            document.getElementById('conversion-result').textContent = resultText;
            document.getElementById('conversion-result').style.display = 'block';
        });
    </script>
</body>
</html>
