isPalindrome = lambda _: _==_[::-1]#불형 회문 판별 함수

word = input().lower()#소문자로 변환

palindromes = []#새로운 리스트 만들기

for start in range(len(word)):
    for end in range(start, len(word)):#이중for문으로 부분회문 찾기
        if isPalindrome(word[start:end+1]):
            palindromes.append(word[start:end+1])#찾으면 새로운 리스트에 추가

palindromes = [w for w in palindromes if len(w) == len(max(palindromes, key=len))]#가장 긴 회문 찾기
palindromes = sorted(list(set(palindromes)))#회문을 찾고 중복 제거를 한 뒤에 리스트를 정렬
for w in palindromes:
    print(w, end=' ')#리스트 내부 값 출력