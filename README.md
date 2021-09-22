# 녹 (Nok)

![logo](logo.png)

**녹 (Nok)** (Korean for _Rust_)

Aren't you 피곤 from writing Rust programs in English? Do you like saying "시발" a lot? Would you like to try something different, in an exotic and funny-sounding language? Would you want to bring some Korean touch to your programs?

nok (Korean for Rust) is here to save your day, as it allows you to write Rust programs in Korean, using Korean keywords, Korean function names, Korean idioms.

You don't feel at ease using only Korean words? Don't worry! Korean Rust is fully compatible with English-Rust, so you can mix both at your convenience.

Here's an example of what can be achieved with nok:

## trait and impl (특성과 구현)

```rust
nok::korean! {
    외부 크레이트 nok;

    사용 std::collections::사전 다음_처럼 Dic;

    열거 EN {
        Oh,
        Hi,
    }

    특성 SomeTrait {
        함수 안녕1(&self, val: 문자열, value: 문자열);
        함수 안녕2(&self, val: 문자열) -> 결과<옵션<&'static 문자열>, 문자열>;
    }

    정적 가변 DICT: 옵션<Dic<문자열, 문자열>> = 없음;

    구조 Something;

    구현 SomeTrait 다음을_위해 Something {
        함수 안녕1(&self, val: 문자열, value: 문자열) {
            여기서 dico = 위험 {
                DICT.get_or_insert_with(기본::default)
            };
            dico.넣기(val, value);
        }
        함수 안녕2(&self, val: 문자열) -> 결과<옵션<&'static 문자열>, 문자열> {
            만약 여기서 있음(dico) = 위험 { DICT.as_ref() } {
                오케이(dico.얻기(&val))
            } 아니면 {
                실패("실패함".into())
            }
        }
    }

    공용(크레이트) 함수 some_thing(i: u32) -> 옵션<결과<u32, 문자열>> {
        만약 i % 2 == 1 {
            만약 i == 42 {
                있음(실패(문자열::다음에서("안녕")))
            } 아니면 {
                있음(오케이(33))
            }
        } 아니면 {
            없음
        }
    }

    비동기 함수 example() {
        구현안됨!()
    }

    #[허용(접근_불가_코드)]
    함수 접근_불가() {
        안돼!("안녕히 가세요.");
        종료!("안녕히 가세요.");
        패닉!("안녕히 가세요.");
    }

    // this is main function
    함수 메인() {
        출력!("{} 오케이 ㅋㅋ", "안녕");
        그냥();
        여기서 test: 문자열 = "Hello World".to_string();
        출력!("test: {}", test);

        여기서 가변 total_sum = 0;
        여기서 result1 = 'main: 무한 {
            다음을_위해 i 안 0..10000 {
                total_sum += i;
                만약 i == 100 {
                    탈출 'main total_sum * 2; // break main and result1 will be total_sum * 2
                }
            }
        };
        출력!("총 합: {}", total_sum);  // 5050
        안돼!("안녕히 가세요.");
    }
}
```

### Support for regional languages

```rust
#[허용(접근_불가_코드)]
함수 접근_불가() {
    안돼!("안녕히 가세요.");
    종료!("안녕히 가세요.");
    패닉!("안녕히 가세요.");
}
```

### Other examples

![korean](https://user-images.githubusercontent.com/2356749/133371209-19fe4e63-09a1-4c02-bad8-999c9849e478.png)

See the [examples](./examples/src/main.rs) to get a rough sense of the whole
syntax.

## 다른 언어

- 프랑스어: [rouille](https://github.com/bnjbvr/rouille)
- 네덜란드어: [roest](https://github.com/jeroenhd/roest)
- 독일어: [rost](https://github.com/michidk/rost)
- 폴란드어: [rdza](https://github.com/phaux/rdza)
- 이탈리아어: [ruggine](https://github.com/DamianX/ruggine)
- 러시아어: [ржавчина](https://github.com/FluxIndustries/rzhavchina)
- 에스페란토: [rustteksto](https://github.com/dscottboggs/rustteksto)
- 힌디어: [zung](https://github.com/rishit-khandelwal/zung)
- 헝가리어: [rozsda](https://github.com/jozsefsallai/rozsda)
- 중국어: [xiu (锈)](https://github.com/lucifer1004/xiu)
- 스페인어: [oxido](https://github.com/fdschonborn/oxido)
- 핀란드어: [ruoste](https://github.com/vkoskiv/ruoste)
- 아랍어: [sada](https://github.com/LAYGATOR/sada)
- 터키어: [pas](https://github.com/ekimb/pas)
- 베트남어: [gỉ](https://github.com/Huy-Ngo/gir)

## 라이선스

[WTFPL](www.wtfpl.net)의 [OLIS](https://olis.or.kr/license/Detailselect.do?lId=1236&mapCode=010183&lType=spdx) 번역판을 약간 변형하여 사용.

