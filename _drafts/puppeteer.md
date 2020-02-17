'use strict';

const puppeteer = require('puppeteer');


(async() => {
	// 크로미엄 실행 headless:false하면 크로미엄 띄움 devtools:true하면 창에 개발자도구 실행되며 뜸
	var browser = await puppeteer.launch({headless: true, devtools: false}); 
	// 새탭 추가
	var page = await browser.newPage();
	
	// 페이지 이동
	await page.goto('주소',{waitUntil: 'networkidle2'});
	
	// 스크립트 실행
	var input = "id";
	var output = await page.evaluate((input) => {
		return document.getElementById(input).value;
	}, input);
	
	// 대기
	await page.waitFor(300);
	
	// 해당 element 찾을 때 까지 대기
	await page.waitForSelector(셀렉터);
	
	// 해당 element 보일 때 까지 대기
	await page.waitForSelector("셀렉터", {'visible':true});
	
	// 해당 element 사라질 때 까지 대기
	await page.waitForSelector("셀렉터", {'hidden':true});
	
	// 해당 element 값이 변경 되었을 때 까지 대기
	await page.evaluate(() => {
		return new Promise(resolve => {
			let selector = "셀렉터";
			let observer = new MutationObserver(function(mutations) {
				if(document.querySelector(selector).textContent.trim() == ""){

				}else{
					resolve();
					observer.disconnect();
				}
			});
			observer.observe(document.querySelector(selector), { childList: true, subtree: true, });
		});
	});
	
	// 페이지 이동시 대기
	await page.waitForNavigation({waitUntil: 'networkidle2'});
	
	// 클릭
	page.click("셀렉터");
	
	// 키입력
	page.type("셀렉터", 입력문구);
	
	
	// 크로미엄 종료
	await browser.close();
	
})();