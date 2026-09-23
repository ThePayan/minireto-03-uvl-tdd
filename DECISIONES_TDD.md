# Diario TDD

## Ciclo 1

### Red
- Prueba añadida:
    test_one_feature_is_tiny
- Técnica de diseño de pruebas empleada:
    Covertura de codigo
- Motivo de elegir este caso:

- Fallo observado:
    Da fallo sin importar que valor provemos

### Green
- Código mínimo escrito:
    def classify_model_size(feature_count: int) -> str:
        return "tiny"

- Resultado de las pruebas:
    Correcto

### Refactor
- Mejora realizada, o motivo por el que no era necesaria:
    No hay duplicación ni estructura que mejorar. Documenta que no se refactoriza todavía.

---

## Ciclo 2

### Red
- Prueba añadida:
    def test_zero_features_is_invalid():
    with pytest.raises(ValueError):
        classify_model_size(0)
- Técnica de diseño de pruebas empleada: Particiones equivalentes
- Motivo de elegir este caso: A partir de un umbral salta error, por lo que deberíamos comprobar los casos límites
- Fallo observado: No se tiene en cuenta  la posibilidad de error

### Green
- Código mínimo escrito:
    
    def classify_model_size(feature_count: int) -> str:
    if feature_count < 1:
        raise ValueError("feature_count debe ser positivo")
    return "tiny"
    
- Resultado de las pruebas:
    Pasan todos los tests

### Refactor
- Mejora realizada, o motivo por el que no era necesaria:

---