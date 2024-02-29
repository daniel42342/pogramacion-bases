DELIMITER //

CREATE FUNCTION fper(emocion VARCHAR(20)) RETURNS VARCHAR(20)
BEGIN
    DECLARE grupo VARCHAR(20);

    -- Asignar grupos según la emoción
    IF emocion = 'negativa' THEN
        SET grupo = 'Grupo de Emociones Negativas';
    ELSEIF emocion = 'positiva' THEN
        SET grupo = 'Grupo de Emociones Positivas';
    ELSE
        SET grupo = 'Otro Grupo'; -- Manejar otras emociones
    END IF;

    RETURN grupo;
END //

DELIMITER ;




SELECT fper('negativa'); -- Devuelve 'Grupo de Emociones Negativas'
SELECT fper('positiva'); -- Devuelve 'Grupo de Emociones Positivas'
