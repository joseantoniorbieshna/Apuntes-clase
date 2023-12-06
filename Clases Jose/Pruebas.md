### Pruebas ortogonales
sería declarar un array, con todas las respuestas esperadas
otro array para el input, de tal manera
que si pones uno encima de otro, pordrías ver cual pertenece a cual
int[] entrada= {5,6,7,8,3,4};
int[] esperada= {5,6,7,8,3,4};

for (int i = 0; i < esperada.length; i++) {
			assertEquals(esperada[i], entrada[i]);
		}
