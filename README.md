#모의고사 

def solution(answers):
    answer = []
    c1,c2,c3 = 0,0,0
    a1 = [1, 2, 3, 4, 5]
    a2 = [2, 1, 2, 3, 2, 4, 2, 5]
    a3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5]

    for i in range(len(answers)):
        b1 = i % 5
        b2 = i % 8
        b3 = i % 10

        if a1[b1] == answers[i]:
            c1 += 1
        if a2[b2] == answers[i]:
            c2 += 1
        if a3[b3] == answers[i]:
            c3 += 1

    k = max(c1,c2,c3)

    if k == c1:
        answer.append(1)
    if k == c2:
        answer.append(2)
    if k == c3:
        answer.append(3)

    return answer
    
 #print(solution([1,2,3,4,5]))

 #ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ
 
 def solution(answers):
    pattern1 = [1,2,3,4,5]
    pattern2 = [2,1,2,3,2,4,2,5]
    pattern3 = [3,3,1,1,2,2,4,4,5,5]
    score = [0, 0, 0]
    result = []

    for idx, answer in enumerate(answers):
        if answer == pattern1[idx%len(pattern1)]:
            score[0] += 1
        if answer == pattern2[idx%len(pattern2)]:
            score[1] += 1
        if answer == pattern3[idx%len(pattern3)]:
            score[2] += 1

    for idx, s in enumerate(score):
        if s == max(score):
            result.append(idx+1)

    return result
