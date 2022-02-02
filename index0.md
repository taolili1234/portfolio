
- 陳金鵬(チンキンホウ)/[中国]

## 正月宿題の問題

- colliderが付いたのに当たり判定が反応なし,以下のよう
[<img src="images/sei-1.png" alt="" style="height: 360px">]()
- 当たったら、画面はこのように表示するが、できなかった最初は
[<img src="images/sei-6.png" alt="" style="height: 360px">]()

### ===========================================================

## なぜこうなるか

- 今回二つの正字の模型は多数のcubeで作られたものでした、以下図のように、最初空のオブジェクトを作て、多数のcubeをぱっと入れて済むと考えましたが、実行した時、当たる反応なし、Tag層も作てますし、cubeにもBOXColliderをいれ済み、コードもちゃんと正しく書いてましたが、Debugして見たら、当たってなかった
間違いない、colliderがどこかでmissしてた。二つの正にあるすべてのcubeのColliderを消して、cubeの親にBOXCollider一つ追加して、実行して、当たった。原因はコード
### ===========================================================
```cs
　　public void OnCollisionEnter(Collision collision)
   {
       if (collision.collider.CompareTag("cube"))
       {
           GameOverLog.SetActive(true);
       }
   }
```

   [<img src="images/sei-2.png" alt="" style="height: 360px">]()


###　===========================================================

## 解決方法

-  解決方法はとても簡単です、Cubeの親だけにColliderを設置すればいいです、完璧ではないが、以下のように

[<img src="images/sei-4.png" alt="" style="height: 360px">]()

[<img src="images/sei-5.png" alt="" style="height: 360px">]()
