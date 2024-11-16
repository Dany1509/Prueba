# Prueba

**Codigo pantalla #1**
From selenium import webdriver
From selenium.webdriver.common.by import By
Import unittest
Class ComunidadesTest(unittest.TestCase):
 Def setUp(self):
 Self.driver = webdriver.Chrome()
 Self.driver.get(“https://coink.com/”)
 Def test_tarjeta_invitacion_comunidades(self):
 Driver = self.driver
 # Seleccionar la opción “Comunidades” en el home
 Comunidades_button = driver.find_element(By.XPATH, “comunidades”)
 Comunidades_button.click()

 # Verificar que aparece la tarjeta de invitación a comunidades
 Invitacion_tarjeta = driver.find_element(By.XPATH, “tarjeta de invitación”)
 Self.assertIsNotNone(invitacion_tarjeta, “La tarjeta de invitación no apareció.”)
 Def test_saldos_en_home(self):
 Driver = self.driver
 # Verificar la visibilidad del Saldo Total
 Saldo_total = driver.find_element(By.XPATH, “saldo total”)
 Self.assertIsNotNone(saldo_total, “El Saldo Total no está visible en el home.”)

 # Verificar la visibilidad del Saldo Disponible
 Saldo_disponible = driver.find_element(By.XPATH, “saldo disponible”)
 Self.assertIsNotNone(saldo_disponible, “El Saldo Disponible no está visible en
el home.”)

 # Comprobar la consistencia de los saldos
 Total_valor = float(saldo_total.text.replace(“$”, “”).replace(“,”, “”))
 Disponible_valor = float(saldo_disponible.text.replace(“$”, “”).replace(“,”, “”))
 # Aquí se puede agregar la lógica para calcular el saldo esperado
 Saldo_esperado = total_valor – 100 # Ejemplo de cálculo
 Self.assertEqual(disponible_valor, saldo_esperado, “El Saldo Disponible no es
consistente.”)
 Def test_navegacion_a_seccion_comunidades(self):
 Driver = self.driver
 # Seleccionar la tarjeta de invitación a comunidades
 Invitacion_tarjeta = driver.find_element(By.XPATH, “tarjeta de invitación”)
 Invitacion_tarjeta.click()

 # Verificar que el usuario es redirigido a la sección de comunidades
 Comunidades_section = driver.find_element(By.XPATH, “selección
comunidades”)
 Self.assertIsNotNull(comunidades_section, “No se redirigió correctamente a
la sección de comunidades.”)
 Def tearDown(self):
 Self.driver.quit()
If __name__ == “__main__”:
 Unittest.main()


**Codigo pantalla 2**
from selenium import webdriver
from selenium.webdriver.common.by import By
import unittest
class ActivacionComunidadTest(unittest.TestCase):
 def setUp(self):
 self.driver = webdriver.Chrome()
 self.driver.get(" https://coink.com/) # Reemplaza con la URL de tu aplicación

 # Iniciar sesión
 self.login()
 def login(self):
 driver = self.driver
 username = driver.find_element(By.NAME, "username")
 password = driver.find_element(By.NAME, "password")
 login_button = driver.find_element(By.NAME, "login")
 username.send_keys("tu_usuario")
 password.send_keys("tu_contraseña")
 login_button.click()
 def test_activacion_comunidad_comfama(self):
 driver = self.driver
 # Seleccionar la opción "Comunidades" en el home
 comunidades_button = driver.find_element(By.XPATH, "opción comunidades")
 comunidades_button.click()

 # Verificar que aparece la opción "Conócelas"
 conoce_button = driver.find_element(By.XPATH, "conocelas")
 conoce_button.click()
 # Seleccionar la comunidad Comfama
 ver_detalles_button = driver.find_element(By.XPATH, "Ver destalles Comfama")
 ver_detalles_button.click()
 # Aceptar términos y condiciones y política de tratamiento de datos
 terminos_checkbox = driver.find_element(By.XPATH, "terminos y condiciones")
 politicas_checkbox = driver.find_element(By.XPATH, "politicas")
 terminos_checkbox.click()
 politicas_checkbox.click()
 # Activar la comunidad Comfama
 activar_button = driver.find_element(By.XPATH, "activar")
 self.assertTrue(activar_button.is_enabled(), "El botón de activar no está
habilitado.")
 activar_button.click()
 # Verificar que la comunidad Comfama aparece en el listado de comunidades
 comunidades_list = driver.find_element(By.XPATH, "listados comunidades")
 self.assertIn("Comfama", comunidades_list.text, "La comunidad Comfama no
aparece en el listado.")
 def tearDown(self):
 self.driver.quit()
if __name__ == "__main__":
 unittest.main()


**Codigo pantalla 3**
from selenium import webdriver
from selenium.webdriver.common.by import By
import unittest
class MovimientoDineroComfamaTest(unittest.TestCase):
 def setUp(self):
 self.driver = webdriver.Chrome()
 self.driver.get(" https://coink.com/")

 # Iniciar sesión
 self.login()
 def login(self):
 driver = self.driver
 username = driver.find_element(By.NAME, "username")
 password = driver.find_element(By.NAME, "password")
 login_button = driver.find_element(By.NAME, "login")
 username.send_keys("tu_usuario")
 password.send_keys("tu_contraseña")
 login_button.click()
 def test_mover_dinero_y_establecer_metas(self):
 driver = self.driver

 # Seleccionar la opción "Comunidades" en el home
 comunidades_button = driver.find_element(By.XPATH, "opción de
comunicades")
 comunidades_button.click()

 # Seleccionar la comunidad Comfama
 comfama_link = driver.find_element(By.XPATH, "comunidad")
 comfama_link.click()
 # Mover dinero a la comunidad
 meter_dinero_button = driver.find_element(By.XPATH, "ingresar dinero ")
 meter_dinero_button.click()
 cantidad_monto = driver.find_element(By.XPATH, "campo monto")
 cantidad_monto.send_keys("50000")
 confirmar_button = driver.find_element(By.XPATH, "confirmar")
 confirmar_button.click()
 # Verificar que el dinero se ha movido a la comunidad
 saldo_total = driver.find_element(By.XPATH, "saldo total")
 self.assertIn("50,000", saldo_total.text, "El dinero se movió correctamente a la
comunidad.")
 # Establecer una meta de ahorro
 establecer_meta_button = driver.find_element(By.XPATH, "establecer meta")
 establecer_meta_button.click()
 nombre_meta = driver.find_element(By.XPATH, "nombre de meta")
 nombre_meta.send_keys("Meta de Prueba")
 monto_meta = driver.find_element(By.XPATH, "monto de meta")
 monto_meta.send_keys("25000")
 confirmar_meta_button = driver.find_element(By.XPATH, "confirmar meta")
 confirmar_meta_button.click()

 metas_list = driver.find_element(By.XPATH, "listado de metas)
 self.assertIn("Meta de Prueba", metas_list.text, "La meta de ahorro se
estableció correctamente.")
 def tearDown(self):
 self.driver.quit()
if __name__ == "__main__":
 unittest.main()


**Código pantalla 4**
from selenium import webdriver
from selenium.webdriver.common.by import By
import unittest
class MetaAhorroTest(unittest.TestCase):
 def setUp(self):
 self.driver = webdriver.Chrome()
 self.driver.get(" https://coink.com/ ") # Reemplaza con la URL de tu aplicación
 # Iniciar sesión
 self.login()
 def login(self):
 driver = self.driver
 username = driver.find_element(By.NAME, "username")
 password = driver.find_element(By.NAME, "password")
 login_button = driver.find_element(By.NAME, "login")
 username.send_keys("tu_usuario")
 password.send_keys("tu_contraseña")
 login_button.click()
 def test_administrar_y_cumplir_meta(self):
 driver = self.driver

 # Navegar a la sección de metas
 metas_button = driver.find_element(By.XPATH, "metas")
 metas_button.click()

 # Verificar la meta existente
 meta_element = driver.find_element(By.XPATH, "meta existente")
 self.assertIsNotNone(meta_element, "No se encontró la meta existente.")
 # Administrar dinero en la meta
 meter_dinero_button = driver.find_element(By.XPATH, "ingresar dinero de
meta")
 meter_dinero_button.click()
 cantidad_monto = driver.find_element(By.XPATH, "monto")
 cantidad_monto.send_keys("10000")
 confirmar_button = driver.find_element(By.XPATH, "confirmar")
 confirmar_button.click()
 # Verificar el progreso de la meta
 progreso_meta = driver.find_element(By.XPATH, "progreso de meta")
 self.assertIn("10,000", progreso_meta.text, "El progreso de la meta no se
actualizó correctamente.")
 # Completar la meta de ahorro
 cumplir_meta_button = driver.find_element(By.XPATH, "cumplir meta")
 cumplir_meta_button.click()
 # Verificar que el dinero se transfirió al saldo disponible
 saldo_disponible = driver.find_element(By.XPATH, "saldo disponible")
 self.assertIn("10,000", saldo_disponible.text, "El dinero no se transfirió
correctamente al saldo disponible.")
 def tearDown(self):
 self.driver.quit()
if __name__ ==


**Código pantalla 5 y Query**
from selenium import webdriver
from selenium.webdriver.common.by import By
import unittest
import time
class AutenticacionTest(unittest.TestCase):
 def setUp(self):
 self.driver = webdriver.Chrome()
 self.driver.get(" https://coink.com/) # Reemplaza con la URL de tu aplicación
 def test_intento_fallido_y_bloqueo(self):
 driver = self.driver
 for i in range(3):
 username = driver.find_element(By.NAME, "username")
 password = driver.find_element(By.NAME, "password")
 login_button = driver.find_element(By.NAME, "login")

 username.send_keys("usuario_incorrecto")
 password.send_keys("contraseña_incorrecta")
 login_button.click()

 # Limpiar campos después de cada intento fallido
 username.clear()
 password.clear()
 # Verificar mensaje de bloqueo
 bloqueo_mensaje = driver.find_element(By.XPATH, "mensaje de bloqueo")
 self.assertIsNotNone(bloqueo_mensaje, "La aplicación no mostró el mensaje
de bloqueo.")
 def test_espera_despues_de_bloqueo(self):
 self.test_intento_fallido_y_bloqueo()

 # Intentar iniciar sesión antes de 15 minutos
 username = driver.find_element(By.NAME, "username")
 password = driver.find_element(By.NAME, "password")
 login_button = driver.find_element(By.NAME, "login")

 username.send_keys("usuario_correcto")
 password.send_keys("contraseña_correcta")
 login_button.click()

 # Verificar que el bloqueo persiste
 bloqueo_mensaje = driver.find_element(By.XPATH, "Mensaje de bloqueo")
 self.assertIsNotNone(bloqueo_mensaje, "El mensaje de bloqueo no persiste
antes de 15 minutos.")

 # Esperar 15 minutos
 time.sleep(15 * 60)

 # Intentar iniciar sesión después de 15 minutos
 username.clear()
 password.clear()
 username.send_keys("usuario_correcto")
 password.send_keys("contraseña_correcta")
 login_button.click()

 # Verificar inicio de sesión exitoso
 bienvenida_mensaje = driver.find_element(By.XPATH, "Mensaje de
bienvenida")
 self.assertIsNotNone(bienvenida_mensaje, "La aplicación no permitió el inicio
de sesión después de 15 minutos.")
 def tearDown(self):
 self.driver.quit()
if __name__ == "__main__":
 unittest.main()
***************************************
SELECT u.user_id, u.document_number, ab.balance AS saldo_total
FROM Users u
JOIN account_balances ab ON u.user_id = ab.user_id
WHERE u.document_number = 'NUMERO_DOCUMENTO';
SELECT u.user_id, u.document_number, pb.balance AS saldo_comunidad
FROM Users u
JOIN account_balances ab ON u.user_id = ab.user_id
JOIN pocket_balances pb ON ab.account_id = pb.account_id
WHERE u.document_number = 'NUMERO_DOCUMENTO';
SELECT u.user_id, u.document_number,
 DATEDIFF(g.end_date, CURDATE()) AS dias_restantes
FROM Users u
JOIN account_balances ab ON u.user_id = ab.user_id
JOIN pocket_balances pb ON ab.account_id = pb.account_id
JOIN goals g ON pb.pocket_id = g.pocket_id
WHERE u.document_number = 'NUMERO_DOCUMENTO';
