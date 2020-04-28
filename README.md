# KorEDA 

이 프로젝트는 [EDA: Easy Data Augmentation Techniques for Boosting Performance on Text Classification Tasks](https://github.com/jasonwei20/eda_nlp) 를 한국어로 쓸 수 있도록 wordnet 부분만 교체한 프로젝트 입니다.

wordnet은 KAIST에서 만든 [Korean WordNet(KWN)](http://wordnet.kaist.ac.kr/) 을 사용했습니다.

EDA에 대한 자세한 내용은 [논문](https://arxiv.org/pdf/1901.11196.pdf)을 참조하시거나 [한글로 번역한 블로그](https://catsirup.github.io/ai/2020/04/21/nlp_data_argumentation.html)를 확인하시면 됩니다.

## 결과

원문 데이터
```plain
제가 우울감을 느낀지는 오래됐는데 점점 개선되고 있다고 느껴요
```
data augmentation한 데이터
```plain
우울감을 느낀지는 오래됐는데 점점 개선되고 있다고	
제가 우울감을 느낀지는 오래됐는데 느껴요 개선되고 있다고 점점	
오래됐는데 우울감을 느낀지는 제가 점점 개선되고 있다고 느껴요	
느껴요 우울감을 느낀지는 오래됐는데 점점 개선되고 있다고 제가
```

## 한계
WordNet만을 단순히 바꿔서 결괏값을 내기 때문에 의미가 변형되어버리는 경우가 생깁니다. 특히 SR과 RI를 사용할 때 많이 발생하는데 **제가 잘못한 건 아닌 것 같아요** 를 **제가 잘못한 총 아닌 것 같아요** (건 -> 총) 으로 바뀌기도 한다. 본 논문에서는 이렇게 바꿔도 꽤나 원문 데이터의 성질을 따라간다고 하지만.. 한국어의 특성상 완전히 따라가기에는 쉽지 않은 것 같다.

안전하게 데이터 증강을 하고 싶다면 RD, RS만을 사용하고, 데이터가 많이 필요하다싶으면 SR과 RI까지 사용하고 인간지능으로 데이터를 걸러내는 작업이 필요할 것이다.
