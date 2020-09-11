import unittest

from selenium.webdriver import Chrome
class TestGoogleSearch(unittest.TestCase):
    def google_url(self):
        driver = Chrome('F://chromedriver.exe')
        driver.maximize_window()
        driver.implicitly_wait(30)
        driver.get('https://www.goolge.com')
        actual_url = driver.current_url

        assert 'Google' in actual_url
        driver.close()

    def google_gmail_link(self):
        driver = Chrome('F://chromedriver.exe')
        driver.maximize_window()
        driver.implicitly_wait(30)
        driver.get('https://www.goolge.com')
        gmail_link = driver.find_element_by_link_text("Gmail")
        status = gmail_link.is_enabled()

        assert status == True
        driver.close()

    def google_gmail_Char(self):
        driver = Chrome('F://chromedriver.exe')
        driver.maximize_window()
        driver.implicitly_wait(30)
        driver.get('https://www.goolge.com')
        search_textbox = driver.find_element_by_name('q')
        max = search_textbox.get_attribute('maxlength')

        assert max == '2048'
        driver.close()
