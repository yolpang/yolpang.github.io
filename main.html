<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>노트북 빌려주세요</title>
    <!-- Tailwind CSS CDN을 사용하여 스타일링 -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Noto Sans KR 폰트 사용 (100: Thin, 400: Regular, 700: Bold) -->
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100;400;700&display=swap">
    <style>
        body {
            font-family: 'Noto Sans KR', sans-serif;
            font-weight: 100; /* 전체 본문을 얇은 폰트로 설정 */
        }
        .loading-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        .popup-message {
            position: fixed;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            z-index: 2000;
            transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out;
            opacity: 0;
            pointer-events: none;
        }
        .popup-message.show {
            opacity: 1;
            transform: translateX(-50%) translateY(0);
        }
        .popup-message.hidden {
            opacity: 0;
            transform: translateX(-50%) translateY(20px);
        }
        .animated-button {
            transition: all 0.2s ease-in-out;
        }
        .animated-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.2), 0 2px 4px -1px rgba(0, 0, 0, 0.1);
        }
        .animated-button:active {
            transform: translateY(0);
            box-shadow: none;
        }
    </style>
</head>
<body class="bg-gray-900 flex items-center justify-center min-h-screen p-4 text-gray-200">
    <div class="max-w-4xl w-full bg-gray-800 rounded-2xl shadow-3xl p-8 space-y-8 transform transition-all duration-300 hover:scale-[1.01]">
        <!-- 시스템 제목 -->
        <h1 class="text-4xl font-extrabold text-center text-white drop-shadow-md">노트북 빌려주세요</h1>
        <!-- 부가 설명 텍스트 -->
         <p class="text-center text-lg font-normal text-gray-400">
                환영합니다! 대여관리 통합 시스템입니다. 신청 현황을 확인 후 신청해주세요! (V25.1)<br>
                내용2 규정 대여기간 등 안내사함
            </p>

        <!-- 메인 화면 섹션 -->
        <div id="mainScreen" class="space-y-8">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <button id="showApplyFormBtn" class="w-full flex justify-center py-4 px-6 border border-transparent rounded-lg shadow-md text-xl font-normal text-white bg-blue-800 hover:bg-blue-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 animated-button">
                    대여하기
                </button>
                <button id="showReturnFormBtn" class="w-full flex justify-center py-4 px-6 border border-transparent rounded-lg shadow-md text-xl font-normal text-white bg-red-800 hover:bg-red-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 animated-button">
                    반납하기
                </button>
            </div>
            
            <!-- 신청 현황 테이블 섹션 -->
            <div class="p-8 bg-gray-700 rounded-2xl shadow-lg">
                <h2 class="text-2xl font-bold text-white mb-6">신청 현황</h2>
                <div class="overflow-x-auto rounded-xl shadow-inner border border-gray-600">
                    <table id="statusTableMain" class="min-w-full divide-y divide-gray-600">
                        <thead class="bg-gray-800">
                            <tr>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">신청 번호</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">신청자 이름</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">노트북 모델</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">전화번호</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">상태</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">신청일시</th>
                            </tr>
                        </thead>
                        <tbody id="tableBodyMain" class="bg-gray-700 divide-y divide-gray-600">
                            <tr>
                                <td colspan="6" class="px-6 py-4 text-sm text-gray-400 text-center">신청 내역을 불러오는 중...</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                <button id="refreshButtonMain" class="mt-6 w-full flex justify-center py-3 px-6 border border-transparent rounded-lg shadow-md text-base font-normal text-white bg-green-800 hover:bg-green-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 animated-button">
                    현황 새로고침
                </button>
            </div>
        </div>

        <!-- 신청 폼 섹션 (초기에는 숨김) -->
        <div id="applyFormSection" class="hidden p-8 bg-gray-700 rounded-2xl shadow-lg">
            <div class="flex items-center justify-between mb-6">
                <h2 class="text-2xl font-bold text-white">노트북 대여 신청하기</h2>
                <button id="backToMainFromApply" class="flex items-center text-gray-400 hover:text-white transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" viewBox="0 0 20 20" fill="currentColor">
                        <path fill-rule="evenodd" d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z" clip-rule="evenodd" />
                    </svg>
                    뒤로가기
                </button>
            </div>
            <form id="applicationForm" class="space-y-6">
                <div>
                    <label for="userName" class="block text-sm font-normal text-gray-300">신청자 이름</label>
                    <input type="text" id="userName" name="userName" required class="mt-2 block w-full px-4 py-2.5 border border-gray-600 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 sm:text-sm bg-gray-800 text-white transition-all">
                </div>
                <div>
                    <label for="laptopModel" class="block text-sm font-normal text-gray-300">노트북 모델</label>
                    <select id="laptopModel" name="laptopModel" required class="mt-2 block w-full px-4 py-2.5 border border-gray-600 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 sm:text-sm bg-gray-800 text-white transition-all">
                        <option value="MacBook Pro 16-A">MacBook Pro 16-A</option>
                        <option value="MacBook Pro 16-B">MacBook Pro 16-B</option>
                        <option value="Galaxy Book Flex 15.6-A">Galaxy Book Flex 15.6-A</option>
                        <option value="Galaxy Book Flex 15.6-B">Galaxy Book Flex 15.6-B</option>
                    </select>
                </div>
                <div>
                    <label for="rentalPeriod" class="block text-sm font-normal text-gray-300">전화번호</label>
                    <input type="text" id="rentalPeriod" name="rentalPeriod" required class="mt-2 block w-full px-4 py-2.5 border border-gray-600 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 sm:text-sm bg-gray-800 text-white transition-all">
                </div>
                <button type="submit" class="w-full flex justify-center py-3 px-6 border border-transparent rounded-lg shadow-md text-base font-normal text-white bg-blue-800 hover:bg-blue-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 animated-button">
                    신청하기
                </button>
            </form>
        </div>
        
        <!-- 반납 폼 섹션 (초기에는 숨김) -->
        <div id="returnFormSection" class="hidden p-8 bg-gray-700 rounded-2xl shadow-lg space-y-8">
            <div class="flex items-center justify-between mb-6">
                <h2 class="text-2xl font-bold text-white">노트북 반납하기</h2>
                <button id="backToMainFromReturn" class="flex items-center text-gray-400 hover:text-white transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" viewBox="0 0 20 20" fill="currentColor">
                        <path fill-rule="evenodd" d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z" clip-rule="evenodd" />
                    </svg>
                    뒤로가기
                </button>
            </div>
            <form id="returnForm" class="space-y-6">
                <div>
                    <label for="returnId" class="block text-sm font-normal text-gray-300">신청 번호</label>
                    <input type="number" id="returnId" name="id" required class="mt-2 block w-full px-4 py-2.5 border border-gray-600 rounded-lg shadow-sm focus:outline-none focus:ring-2 focus:ring-red-500 focus:border-red-500 sm:text-sm bg-gray-800 text-white transition-all" placeholder="신청 번호를 입력하세요">
                </div>
                <button type="submit" class="w-full flex justify-center py-3 px-6 border border-transparent rounded-lg shadow-md text-base font-normal text-white bg-red-800 hover:bg-red-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 animated-button">
                    반납하기
                </button>
            </form>
            
            <!-- 신청 현황 테이블 섹션 (반납 화면에 추가됨) -->
            <div class="p-8 bg-gray-700 rounded-2xl shadow-lg mt-8">
                <h2 class="text-2xl font-bold text-white mb-6">신청 현황</h2>
                <div class="overflow-x-auto rounded-xl shadow-inner border border-gray-600">
                    <table id="statusTableReturn" class="min-w-full divide-y divide-gray-600">
                        <thead class="bg-gray-800">
                            <tr>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">신청 번호</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">신청자 이름</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">노트북 모델</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">전화번호</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">상태</th>
                                <th scope="col" class="px-6 py-3 text-left text-xs font-normal text-gray-400 uppercase tracking-wider">신청일시</th>
                            </tr>
                        </thead>
                        <tbody id="tableBodyReturn" class="bg-gray-700 divide-y divide-gray-600">
                            <tr>
                                <td colspan="6" class="px-6 py-4 text-sm text-gray-400 text-center">신청 내역을 불러오는 중...</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                <button id="refreshButtonReturn" class="mt-6 w-full flex justify-center py-3 px-6 border border-transparent rounded-lg shadow-md text-base font-normal text-white bg-green-800 hover:bg-green-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 animated-button">
                    현황 새로고침
                </button>
            </div>
        </div>
    </div>
    
    <!-- 로딩 오버레이 -->
    <div id="loadingOverlay" class="loading-overlay">
        <svg class="animate-spin h-12 w-12 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
            <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
            <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
        </svg>
    </div>

    <!-- 팝업 메시지 컨테이너 -->
    <div id="popupContainer" class="popup-message hidden">
        <div id="popupMessage" class="rounded-xl shadow-xl px-6 py-4 text-lg font-bold text-center"></div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // 웹 페이지의 각 섹션 및 버튼 요소들을 가져옵니다.
            const mainScreen = document.getElementById('mainScreen');
            const showApplyFormBtn = document.getElementById('showApplyFormBtn');
            const showReturnFormBtn = document.getElementById('showReturnFormBtn');
            const applyFormSection = document.getElementById('applyFormSection');
            const returnFormSection = document.getElementById('returnFormSection');
            const backToMainFromApplyBtn = document.getElementById('backToMainFromApply');
            const backToMainFromReturnBtn = document.getElementById('backToMainFromReturn');
            
            // 두 테이블의 tbody 요소를 각각 가져옵니다.
            const tableBodyMain = document.getElementById('tableBodyMain');
            const tableBodyReturn = document.getElementById('tableBodyReturn');
            const refreshButtonMain = document.getElementById('refreshButtonMain');
            const refreshButtonReturn = document.getElementById('refreshButtonReturn');

            const applicationForm = document.getElementById('applicationForm');
            const returnForm = document.getElementById('returnForm');
            const loadingOverlay = document.getElementById('loadingOverlay');
            const popupContainer = document.getElementById('popupContainer');
            const popupMessage = document.getElementById('popupMessage');
            
            // 전역 변수로 신청 현황 데이터를 저장합니다.
            let latestStatusData = [];

            // --- 이 부분을 실제 Google Apps Script 웹 앱 URL로 바꿔주세요. ---
            const WEB_APP_URL = "https://script.google.com/macros/s/AKfycbzywRTz9cF8lSKLuP7RBz52zFMJm0Q-Lm6QDmq812J3mUN1ZTh2tu6WB70hR_Y2Bbt_/exec";
            
            console.log('WEB_APP_URL:', WEB_APP_URL); 

            // 팝업 메시지를 보여주는 함수
            const showPopupMessage = (message, isError = false) => {
                popupMessage.textContent = message;
                popupMessage.classList.remove('bg-green-600', 'bg-red-600');
                popupMessage.classList.add(isError ? 'bg-red-600' : 'bg-green-600', 'text-white');
                
                popupContainer.classList.remove('hidden');
                setTimeout(() => {
                    popupContainer.classList.add('show');
                }, 10);

                setTimeout(() => {
                    popupContainer.classList.remove('show');
                    popupContainer.classList.add('hidden');
                }, 4000);
            };
            
            // HTML 테이블을 업데이트하는 함수
            const renderTable = (data, targetTableBody) => {
                let contentHtml = '';
                if (data.length === 0) {
                    contentHtml = `<tr><td colspan="6" class="px-6 py-4 text-sm text-gray-400 text-center">신청 내역이 없습니다.</td></tr>`;
                } else {
                    // 데이터를 최신순으로 정렬 (Apps Script에서 가져온 데이터는 오래된 순서입니다)
                    const sortedData = [...data].reverse();

                    sortedData.forEach(row => {
                        let statusColorClass = 'text-gray-400';
                        switch(row[5]) { 
                            case '대기 중': statusColorClass = 'text-gray-400'; break;
                            case '대여 완료': statusColorClass = 'text-green-400'; break;
                            case '반납 신청 완료': statusColorClass = 'text-orange-400'; break;
                            case '반납 완료': statusColorClass = 'text-blue-400'; break;
                            case '신청 불가': statusColorClass = 'text-red-400'; break;
                        }
                        
                        const formattedDate = new Date(row[1]).toLocaleString('ko-KR', {
                            year: 'numeric',
                            month: '2-digit',
                            day: '2-digit',
                            hour: '2-digit',
                            minute: '2-digit'
                        });

                        contentHtml += `
                            <tr class="hover:bg-gray-600 transition-colors duration-200">
                                <td class="px-6 py-4 whitespace-nowrap text-sm font-normal text-gray-200">${row[0]}</td>
                                <td class="px-6 py-4 whitespace-nowrap text-sm font-normal text-gray-400">${row[2]}</td>
                                <td class="px-6 py-4 whitespace-nowrap text-sm font-normal text-gray-400">${row[3]}</td>
                                <td class="px-6 py-4 whitespace-nowrap text-sm font-normal text-gray-400">${row[4]}</td>
                                <td class="px-6 py-4 whitespace-nowrap text-sm font-normal ${statusColorClass}">${row[5]}</td>
                                <td class="px-6 py-4 whitespace-nowrap text-sm font-normal text-gray-400">${formattedDate}</td>
                            </tr>
                        `;
                    });
                }
                targetTableBody.innerHTML = contentHtml;
            };

            // 신청 현황을 불러오는 함수 (API 호출)
            const fetchStatus = async () => {
                if (WEB_APP_URL.includes("YOUR_NEW_URL_HERE")) {
                    const errorMessage = `<tr><td colspan="6" class="px-6 py-4 text-sm text-red-400 text-center">웹 앱 URL을 설정해야 합니다.</td></tr>`;
                    renderTable([], tableBodyMain);
                    renderTable([], tableBodyReturn);
                    tableBodyMain.innerHTML = errorMessage;
                    tableBodyReturn.innerHTML = errorMessage;
                    return;
                }

                loadingOverlay.style.display = 'flex';
                tableBodyMain.innerHTML = `<tr><td colspan="6" class="px-6 py-4 text-sm text-gray-400 text-center">신청 내역을 불러오는 중...</td></tr>`;
                tableBodyReturn.innerHTML = `<tr><td colspan="6" class="px-6 py-4 text-sm text-gray-400 text-center">신청 내역을 불러오는 중...</td></tr>`;

                try {
                    const response = await fetch(WEB_APP_URL);
                    if (!response.ok) {
                        throw new Error(`HTTP 오류! 상태: ${response.status} ${response.statusText}`);
                    }
                    const data = await response.json();
                    
                    if (!Array.isArray(data)) {
                        console.error('Error: Fetched data is not an array.', data);
                        const errorMessage = `<tr><td colspan="6" class="px-6 py-4 text-sm text-red-400 text-center">데이터 형식이 올바르지 않습니다. Apps Script 코드를 확인해 주세요.</td></tr>`;
                        tableBodyMain.innerHTML = errorMessage;
                        tableBodyReturn.innerHTML = errorMessage;
                        return;
                    }

                    // 데이터를 전역 변수에 저장하고 테이블을 업데이트합니다.
                    latestStatusData = data;
                    renderTable(latestStatusData, tableBodyMain);
                    renderTable(latestStatusData, tableBodyReturn);

                } catch (error) {
                    console.error('Error fetching data:', error);
                    const errorMessage = `<tr><td colspan="6" class="px-6 py-4 text-sm text-red-400 text-center">데이터를 불러오는 데 실패했습니다. 오류: ${error.message}</td></tr>`;
                    tableBodyMain.innerHTML = errorMessage;
                    tableBodyReturn.innerHTML = errorMessage;
                } finally {
                    loadingOverlay.style.display = 'none';
                }
            };
            
            // 화면 전환 함수
            const showScreen = (screenId) => {
                // 모든 섹션을 숨깁니다.
                mainScreen.classList.add('hidden');
                applyFormSection.classList.add('hidden');
                returnFormSection.classList.add('hidden');
                
                // 요청된 섹션만 보여줍니다.
                document.getElementById(screenId).classList.remove('hidden');
                
                // 새로운 API 호출 없이, 저장된 데이터로 테이블을 즉시 렌더링합니다.
                // 이렇게 하면 화면 전환 시 로딩 시간이 발생하지 않습니다.
                renderTable(latestStatusData, tableBodyMain);
                renderTable(latestStatusData, tableBodyReturn);
            };

            // 이벤트 리스너 설정
            showApplyFormBtn.addEventListener('click', () => showScreen('applyFormSection'));
            showReturnFormBtn.addEventListener('click', () => showScreen('returnFormSection'));
            backToMainFromApplyBtn.addEventListener('click', () => showScreen('mainScreen'));
            backToMainFromReturnBtn.addEventListener('click', () => showScreen('mainScreen'));
            
            // 새로고침 버튼을 눌렀을 때만 API를 호출합니다.
            refreshButtonMain.addEventListener('click', fetchStatus);
            refreshButtonReturn.addEventListener('click', fetchStatus);

            // 신청 폼 제출 핸들러
            applicationForm.addEventListener('submit', async (event) => {
                event.preventDefault();
                
                if (WEB_APP_URL.includes("YOUR_NEW_URL_HERE")) {
                    showPopupMessage("웹 앱 URL을 설정해야 합니다.", true);
                    return;
                }

                loadingOverlay.style.display = 'flex';
                const formData = new FormData(applicationForm);
                const data = {
                    action: 'apply', 
                    userName: formData.get('userName'),
                    laptopModel: formData.get('laptopModel'),
                    rentalPeriod: formData.get('rentalPeriod')
                };

                try {
                    const response = await fetch(WEB_APP_URL, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'text/plain;charset=utf-8'
                        },
                        body: JSON.stringify(data)
                    });
                    
                    if (!response.ok) {
                        throw new Error(`HTTP 오류! 상태: ${response.status} ${response.statusText}`);
                    }
                    
                    const result = await response.json();
                    
                    if (result.success) {
                        showPopupMessage(result.message);
                        applicationForm.reset();
                        // 신청 성공 후, 최신 현황을 다시 불러옵니다.
                        await fetchStatus(); 
                        showScreen('mainScreen'); // 신청 후 메인 화면으로 돌아가기
                    } else {
                        throw new Error(result.error || "알 수 없는 오류가 발생했습니다.");
                    }
                } catch (error) {
                    console.error('Submission error:', error);
                    showPopupMessage(`신청 실패: ${error.message}`, true);
                } finally {
                    loadingOverlay.style.display = 'none';
                }
            });

            // 반납 폼 제출 핸들러
            returnForm.addEventListener('submit', async (event) => {
                event.preventDefault();
                
                if (WEB_APP_URL.includes("YOUR_NEW_URL_HERE")) {
                    showPopupMessage("웹 앱 URL을 설정해야 합니다.", true);
                    return;
                }
                
                const returnId = document.getElementById('returnId').value;
                loadingOverlay.style.display = 'flex';

                const data = {
                    action: 'return', 
                    id: returnId
                };

                try {
                    const response = await fetch(WEB_APP_URL, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'text/plain;charset=utf-8'
                        },
                        body: JSON.stringify(data)
                        });
                        
                    if (!response.ok) {
                        throw new Error(`HTTP 오류! 상태: ${response.status} ${response.statusText}`);
                    }
                    const result = await response.json();
                    
                    if (result.success) {
                        showPopupMessage(result.message);
                        returnForm.reset();
                        // 반납 성공 후, 최신 현황을 다시 불러옵니다.
                        await fetchStatus(); 
                        showScreen('mainScreen'); // 반납 후 메인 화면으로 돌아가기
                    } else {
                        throw new Error(result.error || "알 수 없는 오류가 발생했습니다.");
                    }
                } catch (error) {
                    console.error('Return error:', error);
                    showPopupMessage(`반납 실패: ${error.message}`, true);
                } finally {
                    loadingOverlay.style.display = 'none';
                }
            });

            // 페이지 로드 시 초기 상태 설정
            fetchStatus();
        });
    </script>
</body>
</html>
