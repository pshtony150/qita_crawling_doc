# QITA Crawling

국제통상협정문서 정량화 프로젝트

## **Update logs**
| Updated date | Features                                                                                                                                                                                                                                                                                                                   | Added Library    |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| 2021-11-03 | <ul><li>SG-exempt의 table 추출 관련 키워드 추가</li><li>국가명 추출 로직 정확도 개선</li></ul> | None |
| 2021-10-26 | <ul><li>작업보드 *2021/10/20*에 대한 변경사항들 적용완료.</li></ul> | `xlsxwriter v3.0.1` |
| 2021-10-19 | <ul><li>**New Extractor**: `SafeGuard Exempt`</li></ul> | None |
| 2021-10-13 | <ul><li>문서 crawling 도중에 에러 발생시, 계속 crawling 할지 묻지 않고 강제로 진행하게 하는 커맨드 옵션(`--force-skip`) 추가.</li></ul> | [See Requirements.txt](https://github.com/pshtony1/QITA-crawling/commit/6ba1e8e27978935b51312712f114b8251bada901#diff-4d7c51b1efe9043e44439a949dfd92e5827321b34082903477fd04876edb7552) |
| 2021-09-27 | <ul><li>많은 양의 문서를 crawling 할시에 간헐적인 네트워크 지연으로 인해 문서를 불러올 수 없었던 문제 해결.</li><li>Extractors 정확도 및 예외 처리 개선</li></ul> | None |
| 2021-09-13 | <ul><li>**(TPR)** TPR Extractor 정확도 개선, 예외 처리 및 기존에 crawling이 불가능하던 문서 패턴에 대해 가능하도록 개선</li></ul> | `fuzzywuzzy v0.18.0` |
| 2021-08-02 | <ul><li>Table Extractor에서 product의 HS digit number들을 가져올 때 다른 값을 가져오던 문제 수정</li></ul> | None |
| 2021-07-26 | <ul><li>**New Extractor**: `TPR` (모든 기능 사용 가능)</li><li>Text crawling 관련 버그 수정 및 코드 개선</li></ul> | None |
| 2021-07-19 | <ul><li>구현이 완료된 모든 extractor에 대해 xlsx 확장자로 export하는 기능 추가</li><li>merge/split 한 결과를 xlsx 확장자로 export하는 기능 추가</li><li>result 폴더 세분화 및 edit 폴더 추가</li><li>document crawling 도중 에러 발생시, crawling을 계속할건지 그만둘건지 선택 가능</li></ul> | `openpyxl v3.0.7` |
| 2021-07-12 | <ul><li>`edit` 커맨드에서 split 기능 추가</li><li>Extractor List 커맨드 개선 및 버그 수정</li><li> `SCM`, `AD` extractor의 코드를 문서의 Table을 추출하는 `Table extractor` 로 확장.</li><li>Table 관련 문서를 2개 이상 추출 시, 이전 테이블의 내용과 현재 테이블의 내용이 합성되던 버그 수정</li><li>Table extractor 에서 crawling 할 table 위에 있는 bold text 를 지정하는 기능 추가</li></ul> | `mypy v0.910` |
| 2021-07-01 | <ul><li>**New Command**: `edit`</li><li>csv의 row들을 merge하는 기능은 추가했지만, split 기능은 아직 추가되지 않음.</li></ul> | None |
| 2021-06-30 | <ul><li>**New Extractor**: `SCM` (모든 기능 사용 가능)</li><li>**(AntiDumping)** 모든 기능 사용 가능</li><li>doc1의 기준이 되는 문자를 초기에 지정하는 단계 추가</li></ul> | None |
| 2021-06-28 | <ul><li>document info의 `country` 추출 알고리즘 변경</li><li>**(Safeguard)** content를 분류하는 알고리즘 개선</li><li>**(AntiDumping)** Export 기능 완료</li></ul> | None |
| 2021-06-26 | <ul><li>**(AntiDumping)** Table 처리시 성능 개선</li><li>**(AntiDumping)** Table 의 content 가 "None" 이던 문서를 올바르게 csv 로 export 하도록 개선</li></ul> | None |
| 2021-06-24 | <ul><li>**New Extractor**: `AntiDumping` (성능 개선 및 기능 추가 필요)</li></ul> | None |
| 2021-06-17 | <ul><li>**Command deprecated**: RunCommand의 `-l`이 `--l` 로 변경되었습니다(기능 동일).</li><li>커맨드로 넣어준 URL이 잘못된 URL로 설정되는 문제 해결</li><li>**(Safeguard)** 크롤링 이후, export 할 csv 파일의 이름 설정 기능 추가</li><li>최초 실행 시, 자동 setting 이후 자동 종료 기능 추가</li></ul> | `readchar v3.0.4`<br/>`psutil v5.8.0`<br/>`pick v1.0.0`  |
| 2021-05-24   | <ul><li>**New Commands**: `update`</li><li>CMD Console에서 텍스트에 색이 적용되지 않던 문제 수정</li><li>크롤링 작업을 진행할 URL 변경 가능</li></ul>                                                                                                                                                                                                                 | None             |
| 2021-05-20   | <ul><li>**New Commands**: `help`, `run`, `test`</li><li>**New Unit-Tests**: `Runcommand`, `SafeguardDocumentExtractor`</li><li>**New Extractor**: `Safeguard`</li><li>`Safeguard` 문서 크롤링 결과를 CSV로 export 할 수 있습니다.</li><li>크롤링 할 `Safeguard` 문서의 **년도**와 **개수**를 설정할 수 있습니다.</li></ul> | `inflect v5.3.0` |

<br />

## **Project Settings**

### Install & Update Dependencies

```
> pip install -r requirements.txt
```

<br />

## **Run**

**⚠ 크롬 브라우저가 설치되어 있어야합니다.**

- **기본 모드로 실행**

    ```
    > python manage.py <Extractor>
    ```

    실행에 있어서 `extractors` 옵션 필드의 영향을 받습니다. 후술할 해당 옵션 항목을 참고해주세요.

    <br />

- **문서 크롤링 모드로 실행**

    ```
    > python manage.py <Extractor> --doc
    ```

    실행에 있어서 `only_a_document` 옵션 필드의 영향을 받습니다. 후술할 해당 옵션 항목을 참고해주세요.

    <br />

- **실행가능한 Extractor들의 목록 출력**

    ```
    > python manage.py --l
    ```

    실행가능한 모든 Extractor들의 약어와 이름을 출력합니다.

    <br />

자세한 실행 방법은 후술할 **Run Options** 항목을 확인해주세요.

<br />

## **Run Options**

실행에 필요한 각종 옵션들을 **`json` 파일**을 이용하여 정해진 규칙에 맞춰 설정할 수 있습니다.

- **옵션 파일 인식 경로**

  해당 파일의 경로는, `json/options.json` 입니다.  
  프로그램 실행 시, 파일이 해당 경로에 존재하지 않는다면 자동으로 생성하며, 모든 설정 값이 기본 값으로 지정된 상태로 생성됩니다.

<br />

- **자동 생성 기능**

    `json/options.json` 의 경로를 찾을 수 없을 때(폴더나 파일이 존재하지 않는 경우) 자동으로 해당 파일이 해당 경로에 생성됩니다.

<br />

- **자동 값 설정 기능**

    대체적으로 올바르지 않은 값 형식이거나, 특정 필드가 비어있는 경우에는 자동으로 값이 설정됩니다.

    이 값은 기본적으로 정해져있는 **기본 값**으로 설정이 되며, 범위가 존재하는 필드의 경우에는 최소 값 혹은 최대 값으로 설정이 되는 경우가 존재합니다.

    또한, 올바르지 않은 `json` 형식일 경우, 파일의 내용을 전부 초기화한 뒤 모든 필드의 값을 default 값으로 설정합니다.

    특정 필드의 값이 비어있는 경우에는, 해당 필드의 값만 default 값으로 초기화합니다.

    <br />

    자동으로 값이 설정되는 경우는 보통 다음과 같습니다.

    - `options.json` 파일의 내용이 비어있는 경우.

    - **파일 내에 올바르지 않은 json 형식이 존재하는 경우.**

        - 이 경우에는 모든 옵션 값이 초기화되니 주의해주세요.

    - 특정 필드의 값이 존재하지 않는 경우.

    - 값의 범위가 지정된 필드에서 해당 범위를 넘어가는 값을 설정한 경우.

    - 넣을 수 있는 값의 종류가 아닌 경우(예를 들어, `a` 필드의 값에는 `"hello"` 나 `"there"` 만 들어올 수 있지만, `"wow"` 라는 값을 넣어준 경우).

    <br />

    이러한 현상이 발생한 경우, `console`창에 '어떤 필드에 어떤 문제가 있어, 자동으로 어떤 값으로 설정합니다' 라는 Warning 구문이 발생합니다.

    - 예1) 경로가 존재하지 않는 경우

        ```
        > python manage.py

        Loading options.json ...

        Warning: such file not found: 'json/options.json'. Therefore, automatically created such directory and file as default value.

        ...
        ```

    - 예2) 특정 필드가 비어있는 경우

        ```
        > python manage.py

        Loading options.json ...

        Warning: The field 'extractors.safeguard' is not defined.
        Therefore, automatically add this field into options as default values.

        Warning: The field 'force_skip' is not defined.
        Therefore, automatically add this field into options as default values.

        ...
        ```

<br />

- **옵션 필드와 Default 값**

    모든 필드와, 그에 대한 default 값은 아래와 같습니다.

    ```json
    {
        "force_skip": false,
        "only_a_document": {
            "url": "",
            "custom_doc_info": {
                "cou": "",
                "doc1": "",
                "doc2": "",
                "date": "",
                "year": ""
            }
        },
        "extractors": {
            "safeguard": {
                "abbreviation": "sg",
                "url": 해당 옵션 설명 참고,
                "year": {
                    "lower": 0,
                    "upper": "inf"
                },
                "crawl_count": "inf",
                "doc1_doc2_separator": "SG"
            },
            "safeguard_exempt": {
                "abbreviation": "sge",
                "url": 해당 옵션 설명 참고,
                "year": {
                    "lower": 2016,
                    "upper": "inf"
                },
                "crawl_count": "inf",
                "doc1_doc2_separator": "SG",
                "keywords": {
                    "main_keywords": [
                        "article 9",
                        "article 9.1",
                        "article 12",
                        "footnote 2"
                    ],
                    "develop_keywords": [
                        "developing countr",
                        "developing nation"
                    ],
                    "except_keywords": [
                        "not apply",
                        "except",
                        "exceiv",
                        "exempt",
                        "exclu"
                    ],
                    "extra_keywords": [
                        "other than"
                    ],
                    "fta_keywords": [
                        "FTA",
                        "Free Trade Agreement"
                    ]
                },
                "keyword_logic": {
                    "table": {
                        "crawl_when_main_keyword_in_content": {
                            "enable": true,
                            "main_keyword_name": "main_keywords"
                        },
                        "if": [
                            {
                                "keyword_sets": [
                                    "main_keywords"
                                ],
                                "use_nlp": false
                            },
                            {
                                "keyword_sets": [
                                    "develop_keywords"
                                ],
                                "use_nlp": false
                            },
                            {
                                "keyword_sets": [
                                    "fta_keywords",
                                    "except_keywords"
                                ],
                                "use_nlp": false
                            }
                        ]
                    },
                    "title": {
                        "if": [
                            {
                                "keyword_sets": [
                                    "main_keywords",
                                    "develop_keywords"
                                ],
                                "use_nlp": false
                            }
                        ],
                        "not_export_cou_if": [
                            {
                                "keyword_sets": [
                                    "develop_keywords",
                                    [
                                        "not",
                                        "except_keywords"
                                    ]
                                ],
                                "use_nlp": false
                            }
                        ]
                    },
                    "paragraph": {
                        "if": [
                            {
                                "keyword_sets": [
                                    "except_keywords"
                                ],
                                "use_nlp": true
                            },
                            {
                                "keyword_sets": [
                                    "develop_keywords"
                                ],
                                "use_nlp": false
                            }
                        ]
                    }
                }
            },
            "anti_dumping": {
                "abbreviation": "ad",
                "url": 해당 옵션 설명 참고,
                "year": {
                    "lower": 0,
                    "upper": "inf"
                },
                "crawl_count": "inf",
                "doc1_doc2_separator": "ADP",
                "table_description": "Original Investigations"
            },
            "subsidies_and_countervailing_measures": {
                "abbreviation": "scm",
                "url": 해당 옵션 설명 참고,
                "year": {
                    "lower": 0,
                    "upper": "inf"
                },
                "crawl_count": "inf",
                "doc1_doc2_separator": "SCM",
                "table_description": "Original Investigations"
            },
            "trade_policy_review": {
                "abbreviation": "tpr",
                "url": 해당 옵션 설명 참고,
                "year": {
                    "lower": 0,
                    "upper": "inf"
                },
                "crawl_count": "inf",
                "doc1_doc2_separator": "TPR"
            }
        }
    }
    ```

    - **`force_skip`**

        | type | 사용가능한 값들 | default 값 |
        | -- | -- | -- |
        | boolean | `true` or `false` | `false` |

        크롤링 진행 시, 오류가 발생했을 때 **크롤링을 이대로 멈출 것인지, 계속할 것인지**를 물어보지 않고 계속해서 진행하게합니다.

        값이 `true` 라면, 바로 계속해서 진행하고, `false` 라면 멈추고 사용자의 응답을 기다립니다.

    <br />

    - **`only_a_document`**

        기존의 크롤링 과정과는 다르게, 특정한 **문서**의 URL을 이용하여 **해당 문서만** 크롤링 할 수 있게 해줍니다.

        이 필드의 옵션들을 설정하고 나면, 아래의 커맨드로 문서 크롤링 모드를 실행할 수 있습니다.

        ```
        > python manage.py <Extractor> --doc
        ``` 

        단, 위 커맨드로 **문서 크롤링 모드를 실행하지 않을 시**, 이 필드의 옵션 값들은 크롤링에 어떠한 영향도 미치지 않습니다.

        또한, **Anti Dumping** 또는 **SCM** Extractor의 `table_description` 옵션이나, **Safeguard Exempt**의 keyword 관련 옵션 같이, 실행시 추가적인 설정을 요구하는 옵션은 해당 Extractor 옵션 필드에서 가져옵니다.

        <br />

        - **`url`**

            | type | 사용가능한 값들 | default 값 |
            | -- | -- | -- |
            | string | 모든 문자열 | `""` (빈 문자열) |

            문서 크롤링 모드로 크롤링할 문서의 URL을 설정할 수 있습니다.

            해당 문서의 URL을 이 필드의 값으로 설정하면 됩니다.  
            예를 들어, `https://docs.w....` 라는 URL을 가진 문서를 크롤링하고 싶다면, 

            ```json
            "only_a_document": {
                "url": "https://docs.w...",
                ...
            }
            ```

            이런 식으로 이 필드에 URL 할당하면 됩니다. 

        <br />

        - **`custom_doc_info`**

            이 필드에 존재하는 모든 값(`cou`, `doc1` 등에 해당하는 필드들의 값)들은 아래의 타입을 가집니다.

            | type | 사용가능한 값들 | default 값 |
            | -- | -- | -- |
            | string | 모든 문자열 | `""` (빈 문자열) |

            해당 값들을 설정하게 되면, export 된 엑셀파일의 column에 해당 값들을 넣을 수 있습니다.  
            또한, 굳이 값들을 설정하지 않더라도 실행에는 지장이 없습니다(예외 존재. 아래 참고).

            예를 들어, 이 필드들의 값이 다음과 같이 설정되어 있다면,

            ```json
            "custom_doc_info": {
                "cou": "GBR",
                "doc1": "G/ADP/N/14/GBR/Add.55",
                "doc2": "G/SCM/N/18/IND/Add.55",
                "date": "",
                "year": "2020",
            }
            ```
            
            Export되는 엑셀파일은 다음과 같습니다.

            | cou | doc1 | doc2 | date | year | HS | ... |
            | -- | - | - | - | - | - | - |
            | GBR | G/ADP/N/14/GBR/Add.55 | G/SCM/N/18/IND/Add.55 | | 2020 | | ... |
            | ... | | | | | | |

            단, 위의 5개의 필드(`cou`, `doc1` 등)와 content 관련 필드를 제외한 다른 필드들(위의 예시에서 `HS`)은 값이 할당되지 않습니다.

            **❗ Safeguard Exempt 중요 사항**

            문서 크롤링 모드를 Safeguard Exempt Extractor로 실행한다면, `cou` 필드의 값을 할당해주는 것을 권장합니다.  
            해당 Extractor 내에는 `cou` 필드를 이용하는 로직이 존재합니다.

    <br />

    - **`extractors`**

        모든 Extractor의 옵션을 담고 있는 필드입니다.

        모든 Extractor가 가지고 있는 공통적인 옵션들을 우선 서술합니다.

        - **공통 옵션**

            - **`abbreviation`**

                | type | 사용가능한 값들 | default 값 |
                | -- | -- | -- |
                | String | 모든 문자열 | Extractor에 따라 다름 |

                각 Extractor의 **약어**를 할당할 수 있는 필드입니다.

                **약어**는 실행 커맨드에 사용할 수 있으며, Extractor의 이름 대신 사용할 수 있습니다.

                예를 들어, 다음과 같이 Safeguard Extractor를 실행할 수 있지만,

                ```
                > python manage.py safeguard
                ```

                이 필드에 할당된 **약어**(`sg`라 가정)를 이용하여 동일한 Extractor를 실행할 수 있습니다.  

                ```
                > python manage.py sg
                ```

                이 필드의 값을 변경하여 원하는 **약어**로 원하는 Extractor를 실행시킬 수 있습니다.
            
            <br />
            
            - **`url`**

                | type | 사용가능한 값들 | default 값 |
                | -- | -- | -- |
                | String | 모든 문자열 | Extractor에 따라 다름 |

                크롤링할 문서들이 담겨있는 URL을 설정합니다.

                기본적으로 각 Extractor 마다 기본으로 할당되는 URL은 아래와 같습니다.

                - Safeguard & Safeguard Exempt

                    [https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=@Symbol=%20g/sg/n/*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true#](https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=@Symbol=%20g/sg/n/*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true#)

                - Anti Dumping

                    [https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=@Symbol=%20g/adp/n/*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true#](https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=@Symbol=%20g/adp/n/*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true#)

                - Subsidies and Countervailing Measures

                    [https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=@Symbol=%20g/scm/n/*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true#](https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=@Symbol=%20g/scm/n/*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true#)

                - Trade Policy Review

                    [https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=@Symbol=%20wt/tpr/m/*%20not%20add*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true#](https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=@Symbol=%20wt/tpr/m/*%20not%20add*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true#)

                이 필드의 URL을 다르게 설정하여 다른 문서 리스트들을 크롤링할 수 있습니다.

                단, 기본적으로 Extractor의 로직은 위 URL에 대한 HTML 구조를 따르기 때문에, 변경한 URL의 HTML 구조도 위 기본 URL과 유사해야만 올바르게 크롤링이 진행됩니다.

                HTML 구조와 관련된 내용은 후술할 **Crawling Logic** 항목을 참고해주세요.
            
            <br />
            
            - **`year`**

                크롤링할 문서의 연도 범위를 설정할 수 있습니다.  

                만약 **`lower`** 필드의 값이 **`upper`** 필드의 값보다 크다면, 그 어떤 문서도 크롤링되지 않습니다.

                **`crawl_count`** 필드와 동시에 연계하여 사용할 수 있습니다.  
                예를 들어, 크롤링할 문서의 연도 범위가 2016~2020년도이고 최신 문서를 100개만 크롤링한다고 하였을 때, 크롤링한 문서를 100개를 채우지 못한 상태에서 연도의 범위가 벗어난다면 그대로 크롤링을 종료합니다.  
                반대로, 문서 개수를 채우고 연도 범위를 벗어나지 않더라도 크롤링을 종료합니다.

                - **`lower`**

                    | type | 사용가능한 값들 | default 값 |
                    | -- | -- | -- |
                    | Integer or string | 0 이상의 모든 정수 또는 `"inf"` | 0 (Safeguard Exempt는 2016) |

                    크롤링될 문서의 가장 낮은 연도를 지정합니다.

                    이 필드의 값이 2020이라면, 2019년도 이하의 문서들은 크롤링이 진행되지 않습니다.

                    값을 `"inf"`(infinity)로 설정하게 되면, 그 어떤 값보다 큰 값으로 인식됩니다. 이는 현재 연도와는 상관이 없습니다.

                <br />

                - **`upper`**

                    | type | 사용가능한 값들 | default 값 |
                    | -- | -- | -- |
                    | Integer or string | 0 이상의 모든 정수 또는 `"inf"` | `"inf"` |

                    크롤링될 문서의 가장 높은 연도를 지정합니다.

                    이 필드의 값이 2005이라면, 2006년도 이상의 문서들은 크롤링이 진행되지 않습니다.

                    값을 `"inf"`(infinity)로 설정하게 되면 크롤링 실행 시, 현재 연도로 자동으로 설정됩니다.

            <br />

            - **`crawl_count`**

                | type | 사용가능한 값들 | default 값 |
                | -- | -- | -- |
                | Integer or string | 0 이상의 모든 정수 또는 `"inf"` | `"inf"` |

                최신 문서를 몇 개까지 크롤링할 것인지를 결정합니다.

                이 필드는 **`year`** 필드와 동시에 연계하여 사용할 수 있습니다.  
                이에 대한 설명은 **`year`** 필드의 설명을 참고해주세요.

                값이 10이라면, 최신 문서를 10개만 크롤링합니다.

                값이 `"inf"` 라면, 크롤링할 문서에 개수 제한을 두지 않습니다.

            <br />

            - **`doc1_doc2_separator`**

                | type | 사용가능한 값들 | default 값 |
                | -- | -- | -- |
                | String | 모든 문자열 | Extractor에 따라 다름 |

                크롤링할 문서의 이름에서, `doc1`과 `doc2`로 분리할 기준을 지정합니다.

                예를 들어 문서의 이름이  
                `G/ADP/N/14/Add.55; G/SCM/N/18/Add.55`  
                이고, 이 필드의 값이 `ADP` 라면,

                `doc1`과 `doc2`는 다음과 같이 분리됩니다.

                | doc1 | doc2 |
                | - | - |
                | G/ADP/N/14/Add.55 | G/SCM/N/18/Add.55 |

            <br />

        이하는 각 Extractor마다 차별되는 옵션을 서술합니다.

        - **`Safeguard`**

            없음.

            <br />

        - **`Safeguard Exempt`**

            - **`keywords`**

                Exempt 관련 Safeguard 문서를 크롤링하기 위한 keyword들의 집합입니다.

                기본적으로 다음과 같은 5개의 keyword 집합을 가지게 되며,

                - `main_keywords`

                - `develop_keywords`

                - `except_keywords`

                - `extra_keywords`

                - `fta_keywords`

                각각의 keyword 마다 사용되는 로직에 차이가 있습니다.

                <br />

                위 5개의 keyword 집합에는 **다른 keyword에 대한 추가/삭제가 가능**합니다.  
                예를 들어 다음과 같이 `main_keywords`가 설정되어 있다면,

                ```json
                "keywords": {
                    "main_keywords": [
                        "article 9",
                        "article 9.1",
                        "article 12",
                        "footnote 2"
                    ],
                    ...
                }
                ```

                여기에 `article 13.2`와 `footnote 3`를 추가하고, `article 9.1`을 삭제하고자 할 때는,

                ```json
                "keywords": {
                    "main_keywords": [
                        "article 9",
                        "article 12",
                        "footnote 2",
                        "article 13.2",
                        "footnote 3"
                    ],
                    ...
                }
                ```

                와 같은 방식으로 keyword를 추가/삭제할 수 있습니다.

                > 당연하지만, keyword를 삭제하게 되면 원하는 특정 문서들이 크롤링되지 않을 수 있으니 이 점은 유의해주세요.

                <br />

                또한 **각 keyword 집합의 이름을 변경할 수 있습니다.**  
                예를 들어, `except_keywords`의 집합 이름을 아래와 같이 변경가능합니다.

                ```json
                "keywords": {
                    ...
                    "my_keywords": [
                        "not apply",
                        "except",
                        "exceiv",
                        "exempt",
                        "exclu"
                    ],
                    ...
                }
                ```

                이렇게 keyword 집합의 이름이 바뀌게 되면, 반드시 **`safeguard_exempt.keyword_logic`** 옵션 필드에서 변경된 keyword 집합 이름들을 변경한 이름으로 설정해주어야합니다.  
                그렇지 않다면, 해당 keyword 집합을 인식하지 못하여 다음과 같은 에러가 발생하게됩니다.

                ```
                ...
                Traceback (most recent call last):
                File "~~~\QITA_Crawling\src\Extractors\Text\Safeguard\safeguard_doc_extractor.py", line 276, in extract    
                    self.task()
                File "~~~\QITA_Crawling\src\Extractors\Text\Safeguard\safeguard_doc_extractor.py", line 213, in task       
                    f"Invalid keyword name '{main_keyword_name}' in JSON option value.\nOption path: extractors.safeguard_exempt.keyword_logic.table.crawl_when_main_keyword_in_content.main_keyword_name"  
                src.utils.exceptions.JSONOptionValueException: 

                ❌ Invalid keyword name '~~~' in JSON option value.
                Option path: extractors.safeguard_exempt.keyword_logic...
                ...
                ```

                <br />

                더 나아가, **원하는 keyword 집합을 새로 생성**할 수 있습니다.  
                예를 들어, `foo`, `bar` 그리고 `we are young` 이라는 키워드들을 가지는 새로운 keyword 집합 `my_new_keyword_group` 을 새로 생성하고 싶다면,

                ```json
                "keywords": {
                    "main_keywords": [
                        "article 9",
                        "article 9.1",
                        "article 12",
                        "footnote 2"
                    ],
                    "develop_keywords": [
                        "developing countr",
                        "developing nation"
                    ],
                    ...
                    "my_new_keyword_group": [
                        "foo",
                        "bar",
                        "we are young"
                    ]
                }
                ```

                위와 같이 다른 keyword 집합의 형식과 동일하게 새로 키워드 그룹을 작성하시면 됩니다.

                물론, 마찬가지로 keyword 집합을 **삭제하는 것도 가능**합니다.

                <br />                

                이하는 각 기본 keyword 집합마다의 설명입니다.

                - **`main_keywords`**

                    | type | 사용가능한 값들 | default 값 |
                    | -- | -- | -- |
                    | List of Strings | 어떠한 문자열이라도 리스트안에 들어가기만하면 상관없음 | 상단의 **옵션 필드와 Default 값** 항목 참고 |

                    해당 문서/문단이 exempt 관련 정보를 포함하는지를 결정하는 keyword들의 집합입니다.

                    이 필드에 담긴 keyword들이 영향을 주는 로직은 기본적으로 다음과 같이 설정되어 있습니다.

                    - Table 크롤링 로직을 실행할 것인가?

                    - 크롤링하기 적절한 Table 인가?

                    - 문단의 title에 대해 크롤링할 것인가?

                    더 자세한 내용은 후술할 **`safeguard_exempt.keyword_logic`** 옵션 필드의 설명을 참고해주세요.

                <br />

                - **`develop_keywords`**

                    | type | 사용가능한 값들 | default 값 |
                    | -- | -- | -- |
                    | List of Strings | 어떠한 문자열이라도 리스트안에 들어가기만하면 상관없음 | 상단의 **옵션 필드와 Default 값** 항목 참고 |

                    특정 문단/문단의 제목이 개발도상국 관련 정보를 포함하는지를 결정하는 keyword들의 집합입니다.

                    이 필드에 담긴 keyword들이 영향을 주는 로직은 기본적으로 다음과 같이 설정되어 있습니다.

                    - 크롤링하기 적절한 Table 인가?

                    - 문단의 title에 대해 크롤링할 것인가?

                    - 문단의 내용에 대해 크롤링할 것인가?

                    더 자세한 내용은 후술할 **`safeguard_exempt.keyword_logic`** 옵션 필드의 설명을 참고해주세요.

                <br />

                - **`except_keywords`**

                    | type | 사용가능한 값들 | default 값 |
                    | -- | -- | -- |
                    | List of Strings | 어떠한 문자열이라도 리스트안에 들어가기만하면 상관없음 | 상단의 **옵션 필드와 Default 값** 항목 참고 |

                    어떤 내용을 **예외한다**는 정보를 포함할 가능성이 있는 keyword들의 집합입니다.

                    이 필드에 담긴 keyword들이 영향을 주는 로직은 기본적으로 다음과 같이 설정되어 있습니다.

                    - 크롤링하기 적절한 Table 인가?

                    - 문단의 내용에 대해 크롤링할것인가?

                    - 크롤링할만한 문단 제목을 가진 문단의 내용에 대해 국가들을 크롤링할 것인가?

                    더 자세한 내용은 후술할 **`safeguard_exempt.keyword_logic`** 옵션 필드의 설명을 참고해주세요.

                <br />

                - **`extra_keywords`**

                    | type | 사용가능한 값들 | default 값 |
                    | -- | -- | -- |
                    | List of Strings | 어떠한 문자열이라도 리스트안에 들어가기만하면 상관없음 | 상단의 **옵션 필드와 Default 값** 항목 참고 |

                    크롤링 로직에 직접 관여하지는 않으며, **특정 경우**에 highlight될 키워드들을 추가할 수 있는 keyword 집합입니다.

                    즉, 어떠한 keyword를 이 필드에 추가한다고 하더라도 크롤링 로직에는 변화가 없으며, export될 파일에서 highlight되는 keyword가 늘어날 뿐입니다.

                    더 자세한 내용은 후술할 **Crawling Logic** 항목을 참고해주세요.

                <br />

                - **`fta_keywords`**

                    | type | 사용가능한 값들 | default 값 |
                    | -- | -- | -- |
                    | List of Strings | 어떠한 문자열이라도 리스트안에 들어가기만하면 상관없음 | 상단의 **옵션 필드와 Default 값** 항목 참고 |

                    FTA(Free Trage Agreement) 관련 정보를 포함하는지를 결정하는 keyword들의 집합입니다.

                    이 필드에 담긴 keyword들이 영향을 주는 로직은 기본적으로 다음과 같이 설정되어 있습니다.

                    - 크롤링하기 적절한 Table 인가?

                    더 자세한 내용은 후술할 **`safeguard_exempt.keyword_logic`** 옵션 필드의 설명을 참고해주세요.

                <br />

            - **`keyword_logic`**

                Safeguard Exempt 크롤링의 핵심 옵션이며, 이 옵션을 이용하여 `keyword logic`을 마음대로 변경할 수 있습니다.

                어떠한 로직으로 크롤링이 진행되는지는 후술할 **Crawling Logic** 항목을 참고해주시고, 여기서는 어떻게 옵션을 설정해야하는지에 대해 설명합니다.

                기본적으로 `keyword logic`이라는 것은, keyword를 이용하여 **크롤링 후보를 선출하는 로직**을 의미합니다.  
                
                그렇기때문에 **Table을 크롤링**하는 `table keyword logic`, **문단의 제목**을 이용하여 크롤링하는 `title keyword logic` 그리고 **문단의 내용**에서 크롤링을 진행하는 `paragraph keyword logic` 이렇게 3가지 `keyword logic`들이 존재하며, 이에 따른 3가지 옵션 필드들이 존재합니다.

                각 `keyword logic`에는 keyword의 그룹을 **논리식으로 조합**하여, '어떠한 keyword들이 존재하면 크롤링을 진행하라' 와 같은 로직을 구현할 수 있습니다.
                
                - **각 `keyword logic`을 구성하는 최소 옵션 단위**

                    가장 기본적인 옵션 단위는 아래와 같은 형식을 가집니다.

                    ```json
                    {
                        "keyword_sets": [
                            "A",
                            "B"
                        ],
                        "use_nlp": false
                    }
                    ```

                    위 옵션 단위가 의미하는 것은 다음과 같습니다.

                    > - keyword 그룹 `A` **그리고** keyword 그룹 `B`에서 각각 **1개 이상의 keyword가 매칭**된다면 크롤링을 진행한다.
                    > 
                    > - 단, 매칭과정에서 **자연어 처리는 사용하지 않는다**. 

                    자연어 처리를 사용하지 않는다는 것은, 매칭 과정에서 keyword를 stemming하지 않고 그대로 매칭하겠다는 뜻 입니다(단, 대소문자는 구분안함).  
                    자연어 처리 로직과 관련해서는 후술할 **Crawling Logic** 항목을 참고해주세요.

                    <br />

                    각 필드의 타입은 아래와 같습니다.

                    - **`keyword_sets`**
                        | type | 사용가능한 값들 | default 값 |
                        | -- | -- | -- |
                        | List of Strings | **`safeguard_exempt.keywords`** 옵션 필드에서 지정한 keyword 그룹명들이 리스트에 담겨야함 | 로직에 따라 다름 |

                    - **`use_nlp`**

                        | type | 사용가능한 값들 | default 값 |
                        | -- | -- | -- |
                        | boolean | `true` or `false` | 로직에 따라 다름 |

                    <br />

                    위 옵션 설정에 대해 일반화를 시켜보자면,  
                    1. `keyword_sets` 필드에는 반드시 **`safeguard_exempt.keywords`** 옵션 필드에서 지정한 keyword 그룹명들이 들어가야한다.

                    2. `keyword_sets`에 지정된 **모든** keyword 그룹들에서 반드시 각각 1개 이상의 keyword가 매칭되어야 크롤링을 진행한다.

                    <br />

                    또한, '특정 keyword 그룹의 keyword가 포함되지 않아야 한다' 도 아래와 같이 설정가능합니다.

                    ```json
                    {
                        "keyword_sets": [
                            "A",
                            "B",
                            ["not", "C"]
                        ],
                        "use_nlp": false
                    }
                    ```

                    위 옵션 단위가 의미하는 것은 다음과 같습니다.

                    > - keyword 그룹 `A`와 `B`에서 각각 1개 이상의 keyword가 매칭되며, keyword 그룹 `C`에서 **매칭되는 keyword가 없어야만 한다.**
                    > 
                    > - 단, 매칭과정에서 **자연어 처리는 사용하지 않는다**. 

                    <br />

                    만약 아래와 같이, `keyword_sets` 필드를 비워둔다면 **항상 크롤링을 진행**하도록 설정합니다.

                    ```json
                    {
                        "keyword_sets": [],
                        "use_nlp": false
                    }
                    ```

                <br/>

                - **`keyword logic` 구성하기**

                    아래와 같이 위에서 설명한 로직의 최소 단위들을 리스트내에 담으면 됩니다.

                    ```json
					"if": [
						{
							"keyword_sets": [
								"A",
								"B",
								"C",
								"D"
							],
							"use_nlp": false
						},
						{
							"keyword_sets": [
								"A",
								["not", "D"]
							],
							"use_nlp": true
						}
					]
                    ```

                    이렇게 로직의 최소 단위들을 모아주게 되면, 서로 **"또는(or)"** 논리식으로 연결됩니다.  
                    이렇게 구성된 로직은 후술할 옵션 필드들에서 사용하게 됩니다.

                    위 로직이 의미하는 것은 다음과 같습니다.

                    > - keyword 그룹 `A`, `B`, `C` 그리고 `D` 에서 각각 1개 이상의 keyword가 매칭되거나, (자연어 처리 사용 x)
                    > 
                    > - **'또는'** keyword 그룹 `A`에서 1개 이상의 keyword가 매칭되고, keyword 그룹 `D`에서 매칭되는 keyword가 없어야만 한다. (자연어 처리 사용 o)

                    <br />

                    만약 아래와 같이 리스트내에 어떠한 최소 단위를 담지 않을 경우,

                    ```json
                    "if": []
                    ```

                    해당 로직은 항상 크롤링되는 로직으로 설정됩니다.

                    <br />

                이하의 내용은 각 `keyword logic`과 관련된 옵션 필드들을 설명합니다.

                - **`keyword_logic.table`**

                    Safeguard Exempt 문서에서 Table을 크롤링하는데 사용할 여러 옵션을 지정합니다.

                    - **`crawl_when_main_keyword_in_content`**

                        기본적으로, Safeguard Exempt Extractor에는 **현재 문서가 exempt 관련 문서일때만** `Table keyword logic`을 실행하여 Table 크롤링 여부를 결정하도록 설정되어 있습니다.

                        이 옵션 필드를 이용하면 exempt 관련 문서인지를 판단하는 keyword 그룹을 설정하거나, 아예 exempt 관련 문서가 아니더라도 `Table keyword logic`을 실행하도록 설정할 수 있습니다.

                        - **`enable`**

                            | type | 사용가능한 값들 | default 값 |
                            | -- | -- | -- |
                            | boolean | `true` or `false` | `true` |

                            현재 문서가 exempt 관련 문서일때만 `Table keyword logic` 실행할 것인지를 결정합니다.

                            값이 `true`라면 exempt 관련 문서일때만 실행하고,
                            값이 `false`라면 exempt 관련 문서에 상관없이 실행합니다.

                        <br />

                        - **`main_keyword_name`**

                            | type | 사용가능한 값들 | default 값 |
                            | -- | -- | -- |
                            | String |  **`safeguard_exempt.keywords`** 옵션 필드에서 지정한 keyword 그룹명 | `"main_keywords"` |

                            현재 문서가 exempt 관련 문서인지를 어떤 keyword 그룹으로 결정할 것인지를 설정합니다.

                            예를 들어 이 필드의 값을 `"main_keywords"` 라고 설정했다면, **`safeguard_exempt.keywords`** 옵션 필드에서 설정한 `main_keywords`라는 keyword 그룹을 가져와, 해당 keyword들 중에 단 하나라도 현재 문서의 모든 내용에서 매칭된다면 현재 문서가 exempt 관련 문서라고 판단합니다.

                        <br />

                    - **`if`**

                        | type | 사용가능한 값들 | default 값 |
                        | -- | -- | -- |
                        | 위에서 설명한 `keyword_logic` | 위의 **`keyword logic` 구성하기** 항목 참고 | 바로 아래 참고 |

                        - **default 값**

                            ```json
                            [
                                {
                                    "keyword_sets": [
                                        "main_keywords"
                                    ],
                                    "use_nlp": false
                                },
                                {
                                    "keyword_sets": [
                                        "develop_keywords"
                                    ],
                                    "use_nlp": false
                                },
                                {
                                    "keyword_sets": [
                                        "fta_keywords",
                                        "except_keywords"
                                    ],
                                    "use_nlp": false
                                }
                            ]
                            ```

                        `Table keyword logic`을 지정합니다.

                        위 로직은 다음과 같습니다.

                        > - keyword 그룹 `main_keywords` 에서 1개 이상의 keyword가 매칭되거나 (자연어 처리 사용 x)
                        > 
                        > - 또는, keyword 그룹 `develop_keywords` 에서 1개 이상의 keyword가 매칭되거나 (자연어 처리 사용 x)
                        >
                        > - 또는, keyword 그룹 `fta_keywords` 와 `except_keywords` 에서 각각 1개 이상의 keyword가 매칭되어야한다. (자연어 처리 사용 x)

                        Table의 description(Table 바로 위 text)이 위 로직에 해당된다면, 해당 Table을 크롤링합니다.

                    <br />

                - **`keyword_logic.title`**

                    Safeguard Exempt 문서에서 문단의 제목을 이용하여 크롤링하는데 사용할 여러 옵션을 지정합니다.

                    - **`if`**

                        | type | 사용가능한 값들 | default 값 |
                        | -- | -- | -- |
                        | 위에서 설명한 `keyword_logic` | 위의 **`keyword logic` 구성하기** 항목 참고 | 바로 아래 참고 |

                        - **default 값**

                            ```json
                            [
                                {
                                    "keyword_sets": [
                                        "main_keywords",
                                        "develop_keywords"
                                    ],
                                    "use_nlp": false
                                }
                            ]
                            ```

                        `Title keyword logic`을 지정합니다.

                        위 로직은 다음과 같습니다.

                        > - keyword 그룹 `main_keywords` 와 `develop_keywords` 에서 각각 1개 이상의 keyword가 매칭되어야한다. (자연어 처리 사용 x)

                        문단의 제목이 위 로직에 해당된다면, 해당 문단의 제목과 문단의 내용을 크롤링합니다.

                        <br />

                    - **`not_export_cou_if`**

                        | type | 사용가능한 값들 | default 값 |
                        | -- | -- | -- |
                        | 위에서 설명한 `keyword_logic` | 위의 **`keyword logic` 구성하기** 항목 참고 | 바로 아래 참고 |

                        - **default 값**

                            ```json
                            [
                                {
                                    "keyword_sets": [
                                        "develop_keywords",
                                        [
                                            "not",
                                            "except_keywords"
                                        ]
                                    ],
                                    "use_nlp": false
                                }
                            ]
                            ```

                        위 로직은 다음과 같습니다.

                        > - keyword 그룹 `develop_keywords` 에서 1개 이상의 keyword가 매칭되고, keyword 그룹 `except_keywords` 에서 매칭되는 keyword가 없어야만 한다. (자연어 처리 사용 x)

                        위의 **`keyword_logic.title.if`** 에서 설정한 `keyword logic`에 해당될 때 실행되는 로직으로, 해당 문단의 내용(content)을 각 문장(sentence)로 분할한 뒤에, **해당 문장에서 국가명이 추출되더라도** 그 문장이 이 필드에서 설정한 로직에 해당된다면, 해당 문장에서 추출된 국가명들을 엑셀 파일에 export 하지 않도록 설정합니다.

                        <br />

                - **`keyword_logic.paragraph`**

                    Safeguard Exempt 문서에서 문단의 내용에서 크롤링을 진행하는데 사용할 여러 옵션을 지정합니다. 

                    - **`if`**

                        | type | 사용가능한 값들 | default 값 |
                        | -- | -- | -- |
                        | 위에서 설명한 `keyword_logic` | 위의 **`keyword logic` 구성하기** 항목 참고 | 바로 아래 참고 |

                        - **default 값**

                            ```json
                            [
                                {
                                    "keyword_sets": [
                                        "except_keywords"
                                    ],
                                    "use_nlp": true
                                },
                                {
                                    "keyword_sets": [
                                        "develop_keywords"
                                    ],
                                    "use_nlp": false
                                }
                            ]
                            ```

                        `Paragraph keyword logic`을 지정합니다.

                        위 로직은 다음과 같습니다.

                        > - keyword 그룹 `except_keywords` 에서 1개 이상의 keyword가 매칭되거나 (자연어 처리 사용 o)
                        > 
                        > - 또는, keyword 그룹 `develop_keywords` 에서 1개 이상의 keyword가 매칭되어야한다. (자연어 처리 사용 x)

                        **여기부터 다시 작성시작하면 됨**
                        문단의 제목이 위 로직에 해당된다면, 해당 문단의 제목과 문단의 내용을 크롤링합니다.

                        <br />

                

        - **`Anti Dumping`**

            - **`table_description`**

                | type | 사용가능한 값들 | default 값 |
                | -- | -- | -- |
                | String | 모든 문자열 | `"Original Investigations"` |

                Table의 **description**을 이용하여 문서에서 크롤링할 Table을 지정할 수 있습니다.

                **Description**은 Table 바로 이전(또는 위)에 나오는 text를 의미합니다.

                **Description**의 매칭 조건은 다음과 같습니다.

                - 대소문자를 구분하지 않습니다.

                - 공백 제거 후, 이 필드에 할당해준 text로 시작해야 합니다.

                예를 들어, `"Original Investigations"`은 다음과 같은 **description**들과 매칭됩니다.

                - `"Original investigations are wonderful."`

                - `"oRiGinalInvestiGations inme?"`

                - `"Original Investigations"`

                - 등등...

        <br />

        - **`Subsidies and Countervailing Measures`**

            - **`table_description`**

                | type | 사용가능한 값들 | default 값 |
                | -- | -- | -- |
                | String | 모든 문자열 | `"Original Investigations"` |

                Table의 **description**을 이용하여 문서에서 크롤링할 Table을 지정할 수 있습니다.

                **Description**은 Table 바로 이전(또는 위)에 나오는 text를 의미합니다.

                **Description**의 매칭 조건은 다음과 같습니다.

                - 대소문자를 구분하지 않습니다.

                - 공백 제거 후, 이 필드에 할당해준 text로 시작해야 합니다.

                예를 들어, `"Original Investigations"`은 다음과 같은 **description**들과 매칭됩니다.

                - `"Original investigations are wonderful."`

                - `"oRiGinalInvestiGations inme?"`

                - `"Original Investigations"`

                - 등등...

        <br />

        - **`Trade Policy Review`**

            없음

<br />

## **Crawling Logic**

Extractor가 어떠한 방식으로 작동하는지 소스 코드와 함께 설명합니다.

모든 Extractor는 크게 아래와 같이 두 가지 유형으로 분류됩니다.

- `List Extractor`

- `Document Extractor`

`List Extractor` 는 **기본 모드**로 프로그램을 실행할 때 `Document Extractor` 보다 먼저 실행되며, 크롤링을 진행할 문서들의 URL 수집, **Pagination**, 문서 정보(doc1, doc2, year 등) 추출 등을 실행합니다.

`Document Extractor` 는 **기본 모드** 또는 **문서 크롤링 모드**에서 실행되며, 크롤링할 문서의 URL로 들어가 내부의 content를 추출하는 역할을 수행합니다.  

<br />

### **Selenium Crawling Logic**

이 프로젝트에서는 웹 크롤링을 진행하기 위해 `selenium` Python 프레임워크를 사용합니다.

이 항목에서는 `selenium` 관련 로직을 설명합니다.

원활한 진행을 위해서 Python 3.7.9 이상의 버전을 사용하는 것을 추천하며, 프로그램 구동에 반드시 **크롬 브라우저**가 필요합니다.

<br />

#### **Opening WebDriver**

`selenium` 프레임워크는 웹 크롤링을 하기 위해 `WebDriver` 를 사용합니다.

`WebDriver`는 기본적으로 브라우저를 구동하여 사용자가 브라우저 자동화를 사용할 수 있게 도와줍니다.

이 프로젝트에서는 `Chrome WebDriver`를 자동으로 설치를 해서 진행하기 때문에, 별도의 추가 설치를 요구하지는 않지만 **크롬 브라우저**는 반드시 설치가 되어있어야 `Chrome WebDriver`를 원활하게 설치할 수 있습니다.
 
`BaseListExtractor` 클래스의 `get_browser` 메소드가 `Chrome WebDriver`를 설치/실행하고 코드에서 사용할 수 있게끔 리턴해줍니다.

```python
# In src/Extractors/Base/list_extractor.py

def get_browser(self):
    options = webdriver.ChromeOptions()
    options.add_argument("--log-level=3")

    return webdriver.Chrome(
        ChromeDriverManager().install(),
        chrome_options=options,
    )
```

모든 `List Extractor`는 위 함수를 직접 아래와 같이 호출하여 `WebDriver`를 구동시킵니다.

```python
# In src/Extractors/Text/Safeguard/safeguard_list_extractor.py

class SafeguardListExtractor(BaseListExtractor):
    def __init__(self, ...):
        self.browser = self.get_browser()

    ...
```

또한, 문서 크롤링 모드로 실행하게 되어도 아래와 같이 `get_browser` 메소드를 호출하여 `WebDriver`를 구동시킵니다.

```python
# In manage.py

def main():
    ...
    def run_doc_extractor(extractor_name):
        browser = BaseListExtractor().get_browser()
        ...
```

이렇게 `WebDriver`를 구동시키게 되면, terminal에 다음과 같은 내용이 출력되며 새로운 크롬 브라우저(정확히는 `WebDriver`)가 켜지게 됩니다.

```
====== WebDriver manager ======
Current google-chrome version is 95.0.4638
Get LATEST driver version for 95.0.4638
Get LATEST driver version for 95.0.4638
Trying to download new driver from https://chromedriver.storage.googleapis.com/95.0.4638.69/chromedriver_win32.zip
...
```

`WebDriver`를 구동시켜 **크롤링 작업이 진행중일 때는 그 어떠한 작업도 `WebDriver`에게 수행시켜서는 안됩니다.**  
예를 들어, 크롤링 작업이 진행중인 `WebDriver`의 URL을 바꾼다던지, 새 탭을 연다던지, 창을 강제로 닫는다던지 등의 작업은 에러를 발생시켜 크롤링 작업을 중단시킬 수 있습니다.  
그러니 원활하게 크롤링이 진행될 수 있도록 방치하시면 됩니다. `Chrome WebDriver`가 구동중이더라도 크롬 브라우저는 사용이 가능합니다.

<br />

#### **Manage WebDriver**

구동중인 `WebDriver`는 기본적으로 어떠한 URL을 가지고 있지 않기 때문에, 이를 설정해주어야 해당 URL로 접근하여 크롤링을 진행할 수 있습니다.

앞서 `get_browser` 메소드로 리턴받은 `WebDriver`의 `get` 메소드를 이용하여 원하는 URL로 이동시킬 수 있습니다.

예를 들어, `WebDriver`를 `https://www.google.com/`로 이동시키고 싶다면,

```python
# WebDriver URL Example
browser = BaseListExtractor().get_browser()
browser.get("https://www.google.com/")
```

와 같이 원하는 URL을 문자열의 형태로 `get` 메소드에 넘겨주면 됩니다.

아래는 이를 이용하여 `options.json`에서 설정한 URL로 `WebDriver`를 이동시키는 로직입니다.

```python
# In src/Extractors/Text/Safeguard/safeguard_list_extractor.py

class SafeguardListExtractor(BaseListExtractor):
    def __init__(self, options):
        self.browser = self.get_browser()
        self.options = options
    ...

    def extract(self):
        # options.json에서 설정해둔 URL로 이동
        self.browser.get(self.options["url"])
```

<br />

#### **HTML element structure to crawl document list**

이 항목에서는 문서 목록들을 크롤링할 수 있는 HTML 구조에 대해서 설명합니다.

![docs wto org_dol2fe_Pages_FE_Search_FE_S_S006 aspx_Query=%40Symbol%3d+g%2fsg%2fn%2f_ Language=ENGLISH Context=FomerScriptedSearch languageUIChanged=true](https://user-images.githubusercontent.com/67461578/142390287-1bd9055f-2acf-4eb9-80ab-d1d7f40e450f.png)

[위 사이트 링크](https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=%40Symbol%3d+g%2fsg%2fn%2f*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true)

위 사이트는 `Safeguad List Extractor`가 가지고 있는 기본 URL 입니다.

요구되는 HTML 구조를 설명하기 전에, 어떠한 방식으로 웹 사이트의 HTML 코드를 확인할 수 있는지를 설명합니다.

- **HTML 코드 확인하기**

    크롬/Firefox/Edge 브라우저를 사용하고 있다면, **F12를 눌러 개발자 도구**를 여시고, 

    ![image](https://user-images.githubusercontent.com/67461578/142391297-88125b9b-496d-43f0-b503-d1e8008f54ab.png)

    위와 같이 **Elements** 항목을 보시면 현재 웹 사이트에 렌더링된 모든 HTML 코드를 보실 수 있습니다. 

    또한 원하는 element의 코드를 보고 싶다면, 원하는 element에서 **마우스 우클릭**하여 **검사**버튼을 눌러 HTML 코드 상에서 해당 element가 위치한 장소로 이동할 수 있습니다.

    ![GIF 2021-11-18 오후 6-51-45](https://user-images.githubusercontent.com/67461578/142392267-945b2422-3dbc-47e5-85e0-9fa7476bc556.gif)

    마지막으로 아래와 같이 **개발자 도구**를 열고 개발자 도구 좌측 상단의 **마우스 아이콘**을 클릭하여 마우스가 위치한 곳의 element에 대한 코드를 바로 확인할 수 있습니다.

    ![GIF 2021-11-19 오후 8-23-25](https://user-images.githubusercontent.com/67461578/142614941-5f9947a4-c9c7-41c0-ac3b-f5497361ca06.gif)

<br />

- **기본적으로 크롤링하는 것들**

    `selenium`이 웹 사이트내의 특정 element를 인식하고 크롤링해오기 위해서는 element의 **id** 혹은 **class**를 이용하거나, 해당 element의 경로를 나타내는 **css selector**, **xpath** 등을 이용할 수 있습니다.  
    이와 관련된 지식이 있어야 후술할 설명들에 대한 원활한 이해가 가능합니다.

    크롤링 로직마다 다른 방식을 사용하며, 이에 대한 자세한 내용은 후술합니다.

    **후술할 크롤링 로직들은 모두 앞서 말한 [사이트 링크](https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S006.aspx?Query=%40Symbol%3d+g%2fsg%2fn%2f*&Language=ENGLISH&Context=FomerScriptedSearch&languageUIChanged=true)를 기준으로 설명합니다.**

    기본적으로 위 사이트에서는 **현재 페이지의 문서들의 목록**과, **Paginator**를 크롤링합니다.

    **현재 페이지의 문서들의 목록**을 가져와 해당 문서의 정보들이나 문서로의 접근을 가능하게 해주고, **Paginator**를 이용하여 다음 페이지로 이동할 수 있게 해줍니다.
    

    - **문서 목록 크롤링**

        `List Extractor`들은 우선적으로 문서 목록을 크롤링합니다.

        크롤링할 문서 목록은 다음과 같이 `table` 태그로 이루어져 있으며, 고유한 id인 `ctl00_MainPlaceHolder_dtlDocs`를 가지고 있습니다.

        ![image](https://user-images.githubusercontent.com/67461578/142617403-1e2751a8-da5d-4e59-b235-4d4be1bb2110.png)

        문서 목록을 가지고 있는 `table` 태그를 추출한 후에는 이 `table` 태그 안에 존재하는 문서 정보 블록들을 추출해냅니다.

        ![image](https://user-images.githubusercontent.com/67461578/142618346-79c48190-af61-420c-9db1-9bca99545899.png)

        문서 정보 블록들은 **css selector**를 이용하여 추출해내며, 경로는 **`table` 태그를 기준**으로 `tbody > tr > td > .hitContainer` 입니다.

        이렇게 `List Extractor`에서는 각 페이지마다 존재하는 모든 문서 정보 블록들을 크롤링하게 됩니다.

        <br />

        이 작업은 `BaseListExtractor`의 `get_all_document_infos` 메서드가 수행하며, 문서 정보 블록들을 리스트에 담아 리턴합니다.

        이 과정에서, `selenium`이 제공하는 `find_element_by_id`, `find_elements_by_css_selector` 메소드들을 이용하여 크롤링을 진행합니다.

        ```python
        # In src/Extractors/Base/list_extractor.py 

        class BaseListExtractor:
            ...

            def get_all_document_infos(self, browser):
                document_table = browser.find_element_by_id(
                    "ctl00_MainPlaceHolder_dtlDocs"
                )

                all_document_infos = document_table.find_elements_by_css_selector(
                    "tbody > tr > td > .hitContainer"
                )

                return all_document_infos
            
            ...
        ```

    <br />

    - **문서 정보와 문서 링크 크롤링**

        `List Extractor`들에서는 앞서 설명한 `get_all_document_infos` 메소드를 호출하여 현재 페이지의 문서 정보 블록들을 받게 됩니다.

        이후에는, 각 문서 정보 블록들에서 해당 문서가 가지고 있는 기본적인 정보들을 크롤링하게 됩니다.

        문서 정보에는 기본적으로 다음과 같은 항목들이 포함됩니다.

        - `document link element`

        - cou
        
        - doc1, doc2

        - date, year

        - product (`Safeguard`, `Safeguard Exempt` 한정)

        - content

        이하는 각 문서 정보들의 크롤링 로직에 대해 설명합니다.  
        content 항목 같은 경우에는 후술할 **`Document Extractor Logics`** 항목을 참고해주세요.

        - **document link element** 추출

            `document link element` 라는 것은, 해당 문서로 이동하기 위한 클릭가능한 element를 의미합니다(간단히 말하면 문서 링크).  
            일반적으로, 각 문서 정보 블록에서 아래와 같은 element를 의미합니다.

            ![image](https://user-images.githubusercontent.com/67461578/142728396-6c40e193-016e-42c7-bedf-374d2577bbf3.png)

            `document link element`는 **css selector**를 이용하여 추출해내며, 경로는 각 **문서 정보 블록을 기준**으로 `.hitSymbol > .FECatalogueSymbolPreviewCss` 입니다.

            이 작업은 `BaseListExtractor`의 `get_document_link_element` 메서드가 수행하며, `document link element`를 리턴해줍니다.

            ```python
            # In src/Extractors/Base/list_extractor.py

            def get_document_link_element(self, document_info):
                try:
                    return document_info.find_element_by_css_selector(
                        ".hitSymbol > .FECatalogueSymbolPreviewCss"
                    )

                except NoSuchElementException:
                    return None
            ```

            만약 해당 element를 찾을 수 없다면 `NoSuchElementException`이 발생하여, `None`을 리턴하게 됩니다.  
            이렇게 `None`이 리턴되면, 각 `List Extractor` 에서는 해당 문서는 건너뛰고 진행하게 되도록 설계되어 있습니다(각 `List Extractor` 코드의 `task` 메소드 참고).
        
        <br />

        - **doc1, doc2** 추출

            `doc1`과 `doc2`는 `document link element`의 text에 포함되기 때문에 우선 `document link element` 를 추출합니다.

            아래와 같은 문서 정보 블록을 예시로 들어 설명합니다.

            ![image](https://user-images.githubusercontent.com/67461578/142729710-5951c5d0-f22d-47a0-af5d-9514765147aa.png)

            1. 우선, 위 문서 정보 블록에서 `document link element`의 text를 가져옵니다.

                ```
                G/L/1304/Suppl.2 ; G/L/1387 ; G/SG/N/12/RUS/3/Suppl.2 ; G/SG/N/12/RUS/4
                ```

            2. 위 text에서 `;`를 기준으로 **문서 번호**를 분리해냅니다.

                ```
                - G/L/1304/Suppl.2
                - G/L/1387
                - G/SG/N/12/RUS/3/Suppl.2
                - G/SG/N/12/RUS/4
                ```

            3. 각 문서 번호를 기준으로 다음 알고리즘을 적용하여 doc1 또는 doc2 인지를 판단합니다.

                - 각 문서 번호를 `/`를 기준으로 분리합니다.

                - `options.json`의 각 Extractor에 대한 `doc1_doc2_separator` 옵션 필드의 값이 분리된 문서 번호에 존재한다면 doc1, 그렇지 않다면 doc2로 결정합니다.

                위 예시에 대해 이 알고리즘을 적용하게 되면 다음과 같은 결과가 나오게 됩니다.

                ```
                doc1_doc2_separator값이 "SG" 라면,
                
                - G/L/1304/Suppl.2          (doc2)
                - G/L/1387                  (doc2)
                - G/SG/N/12/RUS/3/Suppl.2   (doc1)
                - G/SG/N/12/RUS/4           (doc1)
                ```

            4. 분리된 문서 번호를 doc1은 doc1끼리, doc2는 doc2끼리 `;`로 연결합니다.

                ```
                (doc1): G/SG/N/12/RUS/3/Suppl.2;G/SG/N/12/RUS/4
                (doc2): G/L/1304/Suppl.2;G/L/1387
                ```

            코드 상에서는, 우선 `BaseListExtractor`의 `get_all_document_numbers` 메소드를 이용하여 `document link element`의 text를 문서 번호 단위로 분리시켜 줍니다.

            ```python
            # In src/Extractors/Base/list_extractor.py

            def get_all_document_numbers(self, document_link_element):
                document_numbers = document_link_element.text.replace(" ", "").split(";")

                return list(
                    map(
                        lambda document_number: document_number.split("/"),
                        document_numbers
                    )
                )
            ```
            
            <table>
            <tr>
            <td>Inputs</td>
            <td>Returns</td>
            </tr>
            <tr>
            <td>

            ```python
            "G/L/1304/Suppl.2 ; G/L/1387 ; G/SG/N/12/RUS/3/Suppl.2 ; G/SG/N/12/RUS/4"
            ```

            </td>
            <td>

            ```python
            [
                ["G", "L", "1304", "Suppl.2"],
                ["G", "L", "1387"],
                ["G", "SG", "N", "12", "RUS", "3", "Suppl.2"],
                ["G", "SG", "N", "12", "RUS", "4"],
            ]
            ```

            </td>
            </tr>
            </table>

            이렇게 분리된 문서 번호들을 `BaseListExtractor`의 `extract_doc1_doc2` 메소드에 넘겨주어 doc1과 doc2를 얻습니다.

            ```python
            # In src/Extractors/Base/list_extractor.py

            def extract_doc1_doc2(
                self, all_document_numbers, doc1_doc2_separator
            ):
                doc1 = []
                doc2 = []

                for document_number_list in all_document_numbers:
                    document_number = "/".join(document_number_list)

                    if is_contains_text(document_number_list, doc1_doc2_separator):
                        doc1.append(document_number)

                    else:
                        doc2.append(document_number)

                return ";".join(doc1), ";".join(doc2)
            ```

        <br />

        - **cou** 추출

            위의 **`doc1, doc2 추출`** 항목에서 설명한 `get_all_document_numbers` 메소드를 호출하여 얻은 리스트를 이용하여 `cou`를 얻습니다.  
            이해를 돕기 위해 해당 항목을 읽고 와주세요.

            설명을 위해 문서 번호들을 아래 예시로 가정하고 진행합니다.

            ```python
            [
                ["G", "L", "1304", "Suppl.2"],
                ["G", "L", "1387"],
                ["G", "SG", "N", "12", "RUS", "3", "Suppl.2"],
                ["G", "SG", "N", "12", "RUS", "4"],
            ]
            ```

            `cou`는 다음 알고리즘을 이용하여 추출합니다.

            1. 각 문서 번호에서 `"N"`의 인덱스 위치를 구합니다. 만약 각 문서 번호의 리스트에서 `"N"`이 없다면, 해당 문서 번호에서 `cou`를 구하지 않고 넘어갑니다.

                ```
                ["G", "L", "1304", "Suppl.2"] -> "N"이 없으니 넘어감
                ["G", "L", "1387"] -> "N"이 없으니 넘어감
                ["G", "SG", "N", "12", "RUS", "3", "Suppl.2"] -> 인덱스는 2
                ["G", "SG", "N", "12", "RUS", "4"] -> 인덱스는 2
                ```

            2. `1에서 구한 인덱스 + 1` 에 해당하는 원소가 숫자만 포함하고 있으며, `1에서 구한 인덱스 + 2` 에 해당하는 원소가 숫자를 포함하지 않는다면, `1에서 구한 인덱스 + 2` 에 해당하는 원소를 `cou`로 지정합니다. 위의 조건에 만족하지 않는다면, `1에서 구한 인덱스 + 1` 에 해당하는 원소를 `cou`로 지정합니다.

                ```
                ["G", "SG", "N", "12", "RUS"] -> cou는 "RUS"
                ["G", "SG", "N", "KOR", "4"] -> cou는 "KOR"
                ```

            3. 추가로, 2에서 `1에서 구한 인덱스 + 1` 또는 `1에서 구한 인덱스 + 2` 가 배열의 길이를 초과하여 `IndexError`를 발생시킨다면, 해당 문서 번호에서 `cou`를 구하지 않고 넘어갑니다. 

                ```
                ["G", "SG", "N"] -> IndexError 발생
                ["G", "SG", "N", "4"] -> IndexError 발생
                ```

            4. 각 문서번호에서 구한 `cou`들의 중복을 제거합니다.

            위의 예시처럼 리스트로 분리된 문서 번호들을 `BaseListExtractor`의 `extract_country` 메소드에 넘겨주어 `cou`를 얻습니다.

            ```python
            # In src/Extractors/Base/list_extractor.py

            def extract_country(self, all_document_numbers):
                result = []

                for document_number_list in all_document_numbers:
                    try:
                        N_index = document_number_list.index("N")

                        result.append(
                            document_number_list[N_index + 2]
                            if is_contain_digits(document_number_list[N_index + 1])
                            and not is_contain_digits(document_number_list[N_index + 2])
                            else document_number_list[N_index + 1]
                        )

                    except (ValueError, IndexError):
                        pass

                # remove duplicate countries
                return ";".join(list(dict.fromkeys(result)))
            ```

        <br />

        - **date, year** 추출

            우선 `date`와 `year`는 문서 정보 블록의 아래와 같은 element(이하 `document detail element`)에 위치하고 있습니다.

            ![image](https://user-images.githubusercontent.com/67461578/142734693-211c7332-0054-4516-a1c8-5969f222cf1a.png)

            `document detail element`는 **css selector**를 이용하여 추출해내며, 경로는 각 **문서 정보 블록을 기준**으로 `.hitDetail > table` 입니다.

            이 `table` 태그, 즉 `document detail element`에서 찾아야할 `date` text는 아래와 같은 element의 text 입니다.

            ![image](https://user-images.githubusercontent.com/67461578/142734930-fdb2be6d-8cd3-4bc2-9dde-8279910d4870.png)
            
            `document detail element` 내부의 `date` text는 **css selector**를 이용하여 추출해내며, 경로는 각 **`document detail element`를 기준**으로 `tbody > tr > td:nth-child(4) > span` 입니다.  
            위 `tr > td:nth-child(4)` selector의 의미는 `tr` 태그 내부의 4번째 `td` 태그를 의미합니다.

            <br />

            `year` 같은 경우는 `date` text에서 추출해내고, 이 과정들을 `BaseListExtractor`의 `extract_document_date` 메소드에서 수행합니다.

            ```python
            # In src/Extractors/Base/list_extractor.py

            def extract_document_date(self, document_info):
                document_detail_element = (
                    document_info.find_element_by_css_selector(".hitDetail > table")
                )
                document_date = document_detail_element.find_element_by_css_selector(
                    "tbody > tr > td:nth-child(4) > span"
                ).text

                # extract year from date text
                document_year = int(document_date.split("/")[-1])

                return document_date, document_year
            ```

        <br />

        - **product** 추출 (`Safeguard`, `Safeguard Exempt` 한정)

            `product` 라는 것은, 문서 정보 블록내의 다음과 같은 element의 text를 의미합니다.

            ![image](https://user-images.githubusercontent.com/67461578/142735081-342cd5af-5cc1-4d07-8d37-cb3ac7e22c93.png)

            이 text는 **css selector**를 이용하여 추출해내며, 경로는 각 **문서 정보 블록을 기준**으로 `.hitHs > span:last-child` 입니다.  
            위 `.hitHs > span:last-child` selector의 의미는 `hitHs`라는 class를 가지는 태그 내부의 마지막 `span` 태그를 의미합니다.

            만약, 아래와 같이 문서 정보 블록내에 해당 element가 존재하지 않는다면, `product` 값을 빈 문자열(`""`)로 지정합니다.

            ![image](https://user-images.githubusercontent.com/67461578/142735178-103e344e-31ea-4e30-805e-adbd921882b1.png)

            이 과정들을 `BaseListExtractor`의 `extract_product_number` 메소드에서 수행합니다.

            ```python
            # In src/Extractors/Base/list_extractor.py

            def extract_product_number(self, document_info):
                try:
                    document_product_element = (
                        document_info.find_element_by_css_selector(".hitHs > span:last-child")
                    )
                    return document_product_element.text.replace(" ", "")

                except:
                    return ""
            ```

    <br />

    - **`Paginator` 작동시키기**

        `Pagination` 이라는 것은 다음과 같이 문서 목록의 페이지를 이동할 수 있게 해주는 로직을 의미합니다.

        ![image](https://user-images.githubusercontent.com/67461578/142735314-fe2db452-8aa2-4a71-8896-cb204e301a5a.png)

        코드상에서는 위 사진에서의 **`Next`** 버튼만 필요하기 때문에, 해당 element만 크롤링합니다.

        ![image](https://user-images.githubusercontent.com/67461578/142735777-54c4403f-7f82-4437-b0e0-9cb5014116e5.png)

        해당 element는 고유한 id인 `ctl00_MainPlaceHolder_lnkNext`를 가지고 있습니다.

        또한, 다음과 같이 마지막 페이지에서는 **`Next`** element의 태그에 `disabled` 속성이 달려있어, 이 속성이 존재하면 현재 페이지가 마지막 페이지라고 인식을 합니다.

        ![image](https://user-images.githubusercontent.com/67461578/142735839-3e34c1db-f5c5-48de-af2e-b5f9d79c912d.png)

        ![image](https://user-images.githubusercontent.com/67461578/142735880-0282b317-c71d-4e66-b37c-289992b12eea.png)

        **`Next`** 버튼을 가져오는 로직은, `Paginator` 클래스의 `extract_next_button` 메소드가 담당합니다.

        ```python
        # In src/Extractors/Paginator/paginator.py

        def extract_next_button(self):
            next_button = WebDriverWait(self.browser, self.time_out).until(
                EC.presence_of_element_located((By.ID, "ctl00_MainPlaceHolder_lnkNext"))
            )

            # disabled 속성이 있다면, 마지막 페이지로 인식
            if next_button.get_attribute("disabled"):
                self.is_last_page = True

            return next_button
        ```

        위 코드에서 
        ```python
        next_button = WebDriverWait(self.browser, self.time_out).until(
            EC.presence_of_element_located((By.ID, "ctl00_MainPlaceHolder_lnkNext"))
        )
        ```

        부분은 `ctl00_MainPlaceHolder_lnkNext` 라는 id를 가진 element가 브라우저 상에 렌더링될 때까지 최대 `self.time_out`초 동안 기다리겠다는 의미입니다.

        기본 값은 10초로 설정되어 있으며, `Paginator` 클래스의 `__init__` 메소드에서 이 값을 변경할 수 있습니다.

        만약, `self.time_out`초가 지나더라도 버튼이 렌더링되지 않는다면, `selenium`이 `selenium.common.exceptions.TimeoutException` 에러를 일으킵니다.  
        해당 에러가 `extract_next_button` 메소드에서 발생한다면(발생할 가능성은 적지만), 네트워크 문제일 가능성이 높으니 네트워크를 확인해주시거나 `self.time_out`의 값을 더 크게 늘려주시면 됩니다.

        <br />

        `Paginator` 클래스의 또다른 메소드인 `next_page`를 호출하면, **`Next`** 버튼을 클릭하여 `WebDriver`를 다음 페이지로 이동시킵니다.

        ```python
        # In src/Extractors/Paginator/paginator.py

        def next_page(self)
            self.next_button.click()
            self.next_button = self.extract_next_button()
        ```

        <br />

        이 메소드들을 이용하여 모든 `List Extractor`에서는 공통된 `Pagination` 로직을 실행합니다.

        ```python
        # For all List Extractors...

        class ???ListExtractor(BaseListExtractor):
            ...
            def extract(self) -> None:
                ...

                # Pagination Logic
                paginator = Paginator(self.browser)

                while not self.end_crawling:
                    self.task()   # 현재 페이지에 대한 모든 문서 크롤링 진행

                    if paginator.is_last_page:
                        break

                    paginator.next_page()

                ...
        ```

        위 로직에 대한 설명은 다음과 같습니다.

        1. `Paginator` 클래스를 불러온다. 이 과정에서 첫 번째 페이지에 대한 **`Next`** 버튼을 크롤링해온다.

        2. 크롤링이 진행중인 동안, 우선 `self.task` 메소드를 호출하여 현재 페이지에 대해 문서 크롤링을 진행한다.

        3. 현재 페이지가 마지막 페이지라면 크롤링을 중단한다.

        4. 3에서 크롤링이 중단되지 않았다면, 다음 페이지로 넘어간다. 다음 페이지로 넘어감과 동시에 해당 페이지에 대한 **`Next`** 버튼을 크롤링해온다.

        5. 2~4를 반복한다.

        이 로직을 이용해 다음 페이지로 넘어가는 `Paginator`를 작동시키고, 크롤링을 종료시킵니다.

        <br />

#### **Document Extractor Logics**

- **크롤링할 문서로의 이동**

    모든 `Document Extractor` 들은 `List Extractor` 에서 크롤링한 `document link element`를 이용하여 content가 담긴 문서들을 엽니다.

    ```python
    # For all Document Extractors...

    class ???DocumentExtractor(BaseTextDocumentExtractor):
        def __init__(self, browser, document_link_element):
            self.set_members(browser, document_link_element)
            ...

        def task(self):
            # document link element를 클릭하여 문서를 연다
            self.document_link_element.click()
            ...
    ```

    만약 문서 크롤링 모드로 실행했다면, `WebDriver`를 이용하여 직접 문서 URL로 접근하여 문서를 엽니다.

    ```python
    # For all Document Extractors...

    class ???DocumentExtractor(BaseTextDocumentExtractor):
        def task(self):
            # options.json에서 url을 가져와 문서를 연다
            self.browser.get(OptionStorage.get_option("only_a_document.url"))
            ...
    ```

<br />

- **문서의 body 태그 가져오기**

    문서에 접근하여 새 창이 띄워지면, `BaseDocumentExtractor` 클래스의 `get_frame_body` 메소드를 호출하여 실제 content를 담고있는 `body` 태그를 가져옵니다.

    ```python
    # In src/Extractors/Base/doc_extractor.py

    def get_frame_body(
        self, research = False, from_only_a_doc = False
    ):
        FIRST_FRAME = 0
        DOCUMENT_WINDOW = 1
        WAIT_SECONDS = 10

        if not research:
            # Step 1. Switch to opened document
            if not from_only_a_doc:
                self.browser.switch_to.window(
                    self.browser.window_handles[DOCUMENT_WINDOW]
                )

            # Step 2. Switch to iframe which we will extract data
            frame = self.browser.find_elements_by_xpath(
                "//iframe[@id='FrameL']"
            )

            self.browser.switch_to.frame(frame[FIRST_FRAME])

        # Step 3. Get html's body tag from iframe
        frame_body = WebDriverWait(self.browser, WAIT_SECONDS).until(
            EC.presence_of_element_located((By.TAG_NAME, "body"))
        )

        return frame_body
    ```

    위 로직에 대해 잠시 설명하자면, **일반 크롤링 모드**로 `document link element`를 클릭하여 오픈하게 되면, `WebDriver`는 아래와 같이 두 개의 창(window)를 가지게 됩니다.

    <table>
    <tr>
    <td>Window 1 (default)</td>
    <td>Window 2</td>
    </tr>
    <tr>
    <td>

    ![docs wto org_dol2fe_Pages_FE_Search_FE_S_S006 aspx_Query=%40Symbol%3d+g%2fsg%2fn%2f_ Language=ENGLISH Context=FomerScriptedSearch languageUIChanged=true (1)](https://user-images.githubusercontent.com/67461578/142759888-b7b41efb-6458-4e73-800e-9fea8d9bed70.png)
    

    </td>
    <td>


    ![image](https://user-images.githubusercontent.com/67461578/142759917-a7aceb63-8b33-41d0-a0f5-d6d95b295b4a.png)

    </td>
    </tr>
    </table>

    이 상황에서 `selenium`은 `Window 1`을 handling 하고 있기 때문에 handling 하는 창을 문서 창으로, 즉 `Window 2`로 바꿔주어야만 문서의 태그들에 접근을 할 수 있게 됩니다.  
    단, 이 작업은 **문서 크롤링 모드**에서는 에러를 발생시키기 때문에 해당 모드에서는 `get_frame_body` 메소드의 `from_only_a_doc` 인자의 값을 `False`로 할당하여 이 로직이 실행되지 않도록 해야합니다.

    ```python
    # Step 1. Switch to opened document
    if not from_only_a_doc:
        self.browser.switch_to.window(
            self.browser.window_handles[DOCUMENT_WINDOW]
        )
    ```

    또한, 문서의 content는 전부 `iframe`에 들어있기 때문에 `WebDriver`의 `switch_to.frame` 메소드를 이용해 content가 들어있는 `selenium`으로 하여금 `iframe`에 접근을 하게 해주어야 합니다.

    ```python
    # Step 2. Switch to iframe which we will extract data
    frame = self.browser.find_elements_by_xpath(
        "//iframe[@id='FrameL']"
    )

    self.browser.switch_to.frame(frame[FIRST_FRAME])
    ```

    마지막으로, 해당 `iframe`의 `body` 태그가 렌더링 될 때까지 기다리는 코드를 실행하여 `body` 태그를 가져옵니다.

    ```python
    # Step 3. Get html's body tag from iframe
    frame_body = WebDriverWait(self.browser, WAIT_SECONDS).until(
        EC.presence_of_element_located((By.TAG_NAME, "body"))
    )
    ```

    `research` 인자의 목적은 이미 `iframe`에 접근하고 있는 상태에서 다시 `body` 태그를 불러오고 싶을 때 이 인자의 값을 `True`로 만들어주면 다시 `iframe`에 접근하지 않고 불러올 수 있도록 하기 위해 고안되었습니다.

    이렇게 불러온 `body` 태그를 이용하여 문서의 content에 접근할 수 있게 됩니다.

<br />

- **문서의 모든 Text와 Table 관련 태그들 가져오기**

    우선 **`문서의 body 태그 가져오기`** 항목에서 설명했듯이, `body` 태그를 가지고 온 후에는 **각 문단별 text**를 가지고 와야합니다.

    문서의 text 구성 방식을 살펴보자면, 최신 문서들은 각 문단이 `p` 태그로 나뉘어져 있지만 오래된 문서들은 각 문단별로 나뉘어져 있지 않고 `div` 태그로 **한 줄씩** 나뉘어져 있습니다(구두점을 기준으로 한 줄이 아닌 시각적으로 한 줄을 의미. 아래 사진 참고).

    <table>
    <tr>
    <td>최신 문서</td>
    <td>오래된 문서</td>
    </tr>
    <tr>
    <td>

    ![image](https://user-images.githubusercontent.com/67461578/142769637-57453fa0-1c70-4499-8c70-4327d64471e6.png)

    </td>
    <td>

    ![image](https://user-images.githubusercontent.com/67461578/142769583-b21ff95f-5dcd-46df-abb4-70a4f6b47e33.png)

    </td>
    </tr>
    </table>

    따라서 비교적 최신 문서들은 각 문단을 쉽게 추출할 수 있지만, **오래된 문서 같은 경우에는 분리된 줄들을 합쳐주는 작업이 추가적으로 필요**합니다.  
    이 과정에서, `div` 태그의 position style을 이용하여 각 문단을 인식하는 작업을 수행합니다. 이와 관련된 내용은 **Text 추출 작업** 항목에서 후술하겠습니다.

    우선, 문서의 text를 추출하기 위해서 `body` 태그의 `p` 태그들 또는 `div` 태그를 가져와야합니다.  
    확인된 문서들의 태그 패턴들은 다음과 같습니다.
    - 모든 text 들은 `p` 태그들 또는 `div` 태그들 내에 들어있습니다.
        
    - 만약 문서에서 `p` 태그를 사용했다면 `div` 태그를, `div` 태그를 사용했다면 `p` 태그를 사용하지 않는 패턴입니다.

    이러한 패턴을 적용하여 모든 text 관련 태그들을 가져오는 역할을 `BaseTextDocumentExtractor` 클래스의 `extract_text_tags` 메소드가 수행합니다.

    ```python
    # In src/Extractors/Text/Base/text_doc_extractor.py

    def extract_text_tags(
        self,
        frame_body,
        with_table = False,
    ):
        def find_tags(tag_name):
            finded_tags = self.infinity_finding(
                frame_body,
                f"./{tag_name} | ./table" if with_table else f"./{tag_name}",
            )

            if not finded_tags:
                exception_texts = [
                    "cannot be displayed in the viewer",
                    "please click on the pdf link",
                ]

                finded_tags = self.infinity_finding(
                    frame_body,
                    f"./*/{tag_name} | ./*/table" if with_table else f"./*/{tag_name}",
                )

                if not finded_tags and any(
                    map(lambda e: e in frame_body.text.lower(), exception_texts)
                ):
                    return None

            if self.infinity_finding(
                frame_body, f"./{tag_name}/img"
            ) or self.infinity_finding(frame_body, f"./*/{tag_name}/img"):
                return None

            return finded_tags

        p_tags = find_tags("p")
        div_tags = find_tags("div")

        if p_tags is None or div_tags is None:
            return "", None

        if len(p_tags) >= len(div_tags):
            return "p", p_tags

        return "div", div_tags
    ```
    
    위 코드에 대해 설명을 하자면, `find_tags` 함수를 이용해 주어진 태그 이름과 일치하며 문서 내에 존재하는 모든 태그들을 **`xpath` 방식**으로 가져옵니다.  
    이 과정에서 몇 가지 문제가 발생합니다.

    1. **간헐적인 네트워크 오류로 인한 태그 불러오기 오류**

        간혹 네트워크 오류로 인하여 `extract_text_tags` 메소드가 호출되는 시점에 태그들이 렌더링되지 않아 `StaleElementReferenceException` 에러가 발생하는 경우가 존재했습니다.

        이와 같은 경우의 해결책으로 위 코드에서와 같이 `BaseDocumentExtractor` 클래스의 `infinity_finding` 메소드를 호출하여 정상적으로 크롤링될 때 까지 계속해서 태그를 불러오도록 합니다.

        ```python
        # In src/Extractors/Base/doc_extractor.py

        def infinity_finding(self, frame_body, xpath):
            is_stale = True
            finded_tags = []

            while is_stale:
                try:
                    # 인자로 받은 xpath를 이용하여 element들을 추출함
                    finded_tags = frame_body.find_elements_by_xpath(xpath)
                    is_stale = False

                except StaleElementReferenceException:
                    frame_body = self.get_frame_body(research=True) # iframe의 body를 다시 불러옴
                    is_stale = True

            return finded_tags
        ```

    <br />

    2. **문서의 양이 너무 많아 모든 내용이 pdf로 대체된 문서가 존재** 

        ![image](https://user-images.githubusercontent.com/67461578/142770738-9b28ffec-a93e-47c2-90ab-c7c7612b7fe0.png)

        [해당 문서 링크](https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S009-DP.aspx?Language=E&CatalogueIdList=9835,30726,3455,3108,8844,12066,1081,19179,39030,38587&CurrentCatalogueIdIndex=1&FullTextHash=371857150)

        위 문서의 사진과 같이 내용이 너무 길어서 pdf로 대체된 문서 같은 경우에는 크롤링을 진행할 수 없으므로 건너뛰도록 결정합니다.

        ```python
        exception_texts = [
            "cannot be displayed in the viewer",
            "please click on the pdf link",
        ]

        ...

        if not finded_tags and any(
            map(lambda e: e in frame_body.text.lower(), exception_texts)
        ):
            return None
        ```

    <br />

    3. **문서의 모든 내용이 이미지로 되어 있는 문서가 존재**

        [해당 문서 링크](https://docs.wto.org/dol2fe/Pages/FE_Search/FE_S_S009-DP.aspx?language=E&CatalogueIdList=34485,68252,13583,12985,20373,18768,12641,10486&CurrentCatalogueIdIndex=0&FullTextHash=&HasEnglishRecord=True&HasFrenchRecord=True&HasSpanishRecord=True)

        이러한 문서 같은 경우에도 2번과 마찬가지로 크롤링을 진행할 수 없으므로 건너뛰도록 결정합니다.

        ```python
        if self.infinity_finding(
            frame_body, f"./{tag_name}/img"
        ) or self.infinity_finding(frame_body, f"./*/{tag_name}/img"):
            return None
        ```

    앞서 설명한 문제들이 발생하지 않았다면, 추출한 `p` 태그 또는 `div` 태그와 함께 어떤 태그가 추출되었는지 그 이름을 리턴해줍니다.

    ```python
    p_tags = find_tags("p")
    div_tags = find_tags("div")

    if p_tags is None or div_tags is None:
        return "", None

    if len(p_tags) >= len(div_tags):
        return "p", p_tags

    return "div", div_tags
    ```

    만약 `extract_text_tags` 메소드의 인자인 `with_table`의 값이 `True`라면, text 관련 태그들 뿐만이 아니라 table 태그도 함께 추출합니다.

<br />

- **Text 추출 작업**

    **문서의 모든 Text와 Table 관련 태그들 가져오기** 항목에서 서술한듯이, `extract_text_tags` 메소드를 이용하여 text 관련 태그(혹은 table 태그 까지)를 가져왔다면 이 태그들에서 text를 추출하는 작업을 진행합니다.

    - **`Text` 클래스**

        `Text` 클래스는 `src/Extractors/Base/text.py` 에 위치하고 있으며,

        해당 클래스의 인스턴스를 생성하면서 인자로 text 관련 태그(정확히는 `selenium`의 `WebElement` 타입)을 넣어주게 되면 해당 태그의 style 속성 및 text 자동 추출 등을 실행해줍니다.

        ```python
        # In any Document Extractor
        # 필요한 클래스들을 from/import 키워드로 불러왔다고 가정합니다.

        _, tags = self.extract_text_tags(frame_body)
        
        for tag in tags:
            text = Text(tag)

            print(text.text)
            print(text.is_bold)
            print(text.is_underlined)
            print(text.is_italic)
            print(text.is_upper)
            print(text.contains_bold)
            print(text.contains_underlined)
            print(text.contains_italic)
            print()
        ```

        > 출력 예시  
        > 실제 출력에서는 style이 없는 text로 출력되며 이해를 위해 text에 스타일을 추가했습니다.
        > 
        > **Lorem ipsum there is so many features...**  
        > True  
        > False  
        > False  
        > False  
        > True  
        > False  
        > False  
        > 
        > ***HEY, MY NAME IS JAMES***  
        > True  
        > False  
        > True  
        > True  
        > True  
        > False  
        > True  
        >   
        > **HEY**, my name **IS** *JAMES*  
        > False  
        > False  
        > False  
        > False  
        > True  
        > False  
        > True  
        >   
        > <u>HEY</u>, my name IS JAMES  
        > False  
        > False  
        > False  
        > False  
        > False  
        > True  
        > False  

        위 예시와 같이 `Text` 클래스는 style과 관련된 여러가지 멤버를 가지고 있습니다.

        이 클래스의 유용한 멤버들을 나열하자면,

        - `text`: 추출한 text를 담고 있습니다.

        - `is_bold`: text 전체가 **bold** 인지 체크합니다. 부분적으로 **bold**라면 `False` 입니다.

        - `contains_bold`: text 중 일부가 **bold** 인지 체크합니다. 전체가 **bold**더라도 `True` 입니다.

        - `is_underlined`: text 전체가 <u>underlined</u> 인지 체크합니다. 부분적으로 <u>underlined</u>라면 `False` 입니다.

        - `contains_underlined`: text 중 일부가 <u>underlined</u> 인지 체크합니다. 전체가 <u>underlined</u>이더라도 `True` 입니다. 

        - `is_italic`: text 전체가 <i>italic</i> 인지 체크합니다. 부분적으로 <i>italic</i>라면 `False` 입니다.

        - `contains_italic`: text 중 일부가 <i>italic</i> 인지 체크합니다. 전체가 <i>italic</i>이더라도 `True` 입니다. 

        - `is_upper`: text 전체가 대문자로 이루어져있는지 체크합니다.

        - `style`: 인스턴스 생성시 입력받았던 태그의 `style` attribute 값을 담고 있습니다.

        <br />

        또한, `Text` 클래스에 태그를 넘겨주면서 해당 태그의 특정 자식 태그를 제외할 수 있습니다. 

        예를 들어, text를 추출할 태그의 자식 태그들중 `sup` 태그와 `a` 태그를 제외하고 싶다면

        ```python
        text = Text(tag, skip_tags=["sup", "a"])
        ```

        처럼 `skip_tags` 인자를 활용해주시면 됩니다.

    <br />

    - **text 태그가 `div` 태그일 때**

        **문서의 모든 Text와 Table 관련 태그들 가져오기** 항목에 서술된 대로, 오래된 문서 같은 경우에는 `div` 태그로 분리된 text들을 합쳐주는 작업이 필요합니다.

        해당 작업은 `BaseTextDocumentExtractor` 클래스의 `concat_div_texts` 에서 수행합니다.

        ```python
        # In src/Extractors/Text/Base/text_doc_extractor.py

        def concat_div_texts(self, texts):
            result = []
            cur_top: float = float("-inf")

            for text in texts:
                if text.position["top"] is None or text.position["left"] is None:
                    continue

                if text.position["top"] > cur_top:
                    result.append(text)
                    cur_top = text.position["top"]

                elif text.position["top"] == cur_top:
                    result[-1].concat(text)
                    result[-1].position["left"] = text.position["left"]

                if len(result) >= 2:
                    if (
                        result[-2].is_upper
                        and not result[-2].text.endswith(tuple(digits))
                        and result[-1].is_upper
                        and result[-2].position["left"] == result[-1].position["left"]
                    ):
                        result[-2].concat(result[-1])
                        result.pop()

            return result
        ```

        `div` 태그들을 위 메소드에 넘겨주면, 분리된 text들을 연결해줍니다.

## **Extractor types**

### Safeguard

- Crawling type: `Text`

- Example document structure

  ```
  This is the example!

  1 The Wonderful Day

  A. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Nisl tincidunt eget nullam non.
  
  B. Quis hendrerit dolor magna eget est lorem ipsum dolor sit. Volutpat odio facilisis mauris sit amet massa.

  2 Hello my name is lorem

  Senectus et netus et malesuada. Nunc pulvinar sapien et ligula ullamcorper malesuada proin. Neque convallis a cras semper auctor. Libero id faucibus nisl tincidunt eget. Leo a diam sollicitudin tempor id. A lacus vestibulum sed arcu non odio euismod lacinia. In tellus integer feugiat scelerisque.

  ...
  ```

- Export document strcture

  | cont_name | cont |
  | --------- | ---- |
  | intro | This is the example! |
  | 1 The Wonderful Day | A. Lorem ipsum dolor sit ame... B. Quis hendrerit dolor ... |
  | 2 Hello my name is lorem | Senectus et netus et malesuada. Nunc pulvinar sapien et ligula ullamcorper malesuada proin. Neque convallis a cras semper auct... |

<br />

### Safeguard Exempt

- Crawling type: `Text` and `Table`

<br />

### Trade Policy Review

- Crawling type: `Text`

- Example document structure

  ```
  1. The Wonderful Day

  1.1. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Nisl tincidunt eget nullam non.
  
  1.2. Quis hendrerit dolor magna eget est lorem ipsum dolor sit. Volutpat odio facilisis mauris sit amet massa.


  2. Hello my name is lorem

  2.1. Senectus et netus et malesuada.
  
  2.2. Nunc pulvinar sapien et ligula ullamcorper malesuada proin.
  
  UNITED STATES
  
  2.3. Neque convallis a cras semper auctor. 
  
  2.4. Libero id faucibus nisl tincidunt eget.
  
  WOW

  2.5. Leo a diam sollicitudin tempor id.

  ...
  ```

- Export document strcture

  | cont_name | cont_cou(sub_cont_name) | cont |
  | --------- | ---- | -- |
  | 1. The Wonderful Day | | 1.1. Lorem ipsum dolor sit amet, co... |
  | 1. The Wonderful Day | | 1.2. Quis hendrerit dol... |
  | 2. Hello my name is lorem | | 2.1. Senectus et net... |
  | 2. Hello my name is lorem | | 2.2. Nunc pulvinar sapien et l... |
  | 2. Hello my name is lorem | UNITED STATES | 2.3. Neque convallis a cr... |
  | 2. Hello my name is lorem | UNITED STATES | 2.4. Libero id faucibus ni... |
  | 2. Hello my name is lorem | WOW | 2.5. Leo a diam so... |


<br />

### AntiDumping, Subsidies and countervailing measures

- Crawling type: `Table`

  You can crawl any table in document.
