# Handling-Child-Browsers
Write a script for the following scenario, 1) Count the number of browsers opened  2) Print the page title for all the opened browsers

	public static void main(String[] args) throws InterruptedException 
	{
		FirefoxDriver driver = new FirefoxDriver();
		driver.get("http:www.naukri.com");
    
		Set<String> allbrowser = driver.getWindowHandles();
		int count = allbrowser.size();
		System.out.println(count);
    
		for (String wh:allbrowser)
		  {
			  driver.switchTo().window(wh);
			  String title = driver.getTitle();
			  System.out.println(title);
			  driver.close();
		  }
	 }
