// mobile_app/lib/models/lunar_model.dart (Дополнение)

// ... (существующие enum LunarPhaseType, CraterFeature, AstrophotoPlan - остаются прежними) ...

// Данные о текущем положении Луны, включая Либрацию
class EphemerisData {
  // ... (предыдущие поля: datetime, phaseFraction, illuminatedPercent, altitudeDegrees, azimuthDegrees, distanceKm, colongitudeDegrees) ...
  final double librationLat; // Либрация по широте (Libration in Latitude)
  final double librationLon; // Либрация по долготе (Libration in Longitude)
  
  EphemerisData({
    // ... (предыдущие обязательные поля) ...
    required this.librationLat, required this.librationLon
  });
}

// Условия наблюдения
class ObservationConditions {
  final double cloudCoverPercent; // Процент облачности (0-100)
  final double seeingQualityArcsec; // Качество атмосферной прозрачности (Seeing, в угловых секундах)
  final int bortleScale; // Шкала Бортля для светового загрязнения (1=идеально, 9=город)

  ObservationConditions({
    this.cloudCoverPercent = 0.0,
    this.seeingQualityArcsec = 2.0, // 2.0" - среднее
    this.bortleScale = 4,
  });
}

// Оборудование пользователя
class TelescopeSetup {
  final String model;
  final double focalLengthMm; // Фокусное расстояние
  final double apertureMm; // Апертура (диаметр)
  
  TelescopeSetup({
    required this.model, required this.focalLengthMm, required this.apertureMm
  });
}

// Расчет поля зрения для конкретного объектива/окуляра
class FieldOfView {
  final double magnification; // Увеличение (Zoom)
  final double trueFieldOfViewDegrees; // Истинное поле зрения
  final double exitPupilMm; // Выходной зрачок
  
  FieldOfView({required this.magnification, required this.trueFieldOfViewDegrees, required this.exitPupilMm});
}
