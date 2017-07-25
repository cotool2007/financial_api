# Financial Services – Financial API - Part 2: Read and Write API Security Profile

## Warning

This document is not an OIDF International Standard. It is distributed for review and comment. It is subject to change without notice and may not be referred to as an International Standard.

この文書はOIDF国際標準ではありません。 レビューとコメントのために配布されています。 これは予告なしに変更されることがあり、国際標準とは呼ばれない場合があります。  

Recipients of this draft are invited to submit, with their comments, notification of any relevant patent rights of which they are aware and to provide supporting documentation.

この草案の受領者は、彼らのコメントと共に、彼らが認識している関連する特許権の通知を提出し、裏付け文書を提出するよう求められる。

## Copyright notice

The OpenID Foundation (OIDF) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OIDF as the source of the material, but that such attribution does not indicate an endorsement by the OIDF.

OpenID Foundation（OIDF）は、貢献者、開発者、実装者、または他の利害関係者に、この実施者草案または最終仕様書の複製、派生作品の作成、配布、実行および表示のための非独占的で無償の世界的著作権ライセンスを付与する （i）仕様書を作成する目的のみで、（ii）OIDFの原資料としての帰属が条件であるが、そのような帰属が裏書を示すものではない場合は、そのような書類に基づいて実施者草案および最終仕様を実施する OIDFによって

The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation and others. Although the OpenID Foundation has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The OpenID Foundation and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The OpenID Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The OpenID Foundation invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.

この仕様に記述されている技術は、OpenID Foundationのメンバーなど、さまざまなソースから寄せられたものです。 OpenID Foundationは、この技術が流通可能であることを保証するための措置を講じていますが、以下に記載されている技術の実装または使用に関連すると思われる知的財産権その他の権利の有効性または範囲については、この仕様またはそのような権利に基づくライセンスが利用可能であるかどうか。そのような権利を特定するために何らかの独立した努力をしたことを示すものでもありません。 OpenID Foundationと本仕様書の貢献者は、商品性、非侵害性、特定の目的への適合性、またはタイトルに関する黙示的保証を含め、明示的にも黙示的にも（これに限定されない）この仕様の実装に関するリスク全体が実装者によって想定されます。 OpenIDの知的財産権ポリシーでは、寄稿者は他の寄稿者や実施者に対して特定の特許クレームを主張しないという特許約束を提供する必要があります。 OpenID Foundationは、この仕様を実践するのに必要な技術を網羅する可能性のある著作権、特許、特許出願、またはその他の所有権を、関心を持つ関係者に注意を促すよう呼びかけます。

## Foreword

OIDF (OpenID Foundation) is an international standardizing body comprised by over 160 participating entities (work group participants). The work of preparing international standards is carried out through OIDF work groups according to OpenID Process. Each participants interested in a subject for which a work group has been established has the right to be represented on that work group. International organizations, governmental and non-governmental, in liaison with OIDF, also take part in the work. OIDF collaborates closely with other standardizing bodies in the related fields.

OIDF（OpenID Foundation）は、160を超える参加企業（ワークグループ参加者）が構成する国際標準化機関です。 国際標準を作成する作業は、OpenIDプロセスに従ったOIDFワークグループを通じて実行されます。 ワークグループが設立された対象に関心がある各参加者は、そのワークグループに代表される権利があります。 OIDFと連携している政府機関や非政府組織も、この作業に参加しています。 OIDFは関連分野の他の標準化機関と密接に協力しています。

OpenID Foundation standards are drafted in accordance with the rules given in the OpenID Process.

OpenID Foundation標準は、OpenIDプロセスで与えられた規則に従って作成されています。

The main task of work group is to prepare Implementers Draft and Final Draft. Final Draft adopted by the Work Group through consensus are circulated publicly for the public review for 60 days and for the OIDF members for voting. Publication as an OIDF Standard requires approval by at least 50 % of the members casting a vote.

ワークグループの主な任務は、実施者草案と最終草案を準備することです。 ワークグループがコンセンサスで採択した最終草案は、公開審査のために60日間公開され、OIDF加盟国は投票する。 OIDF基準としての公表には、投票を行ったメンバーの少なくとも50％の承認が必要です。

Attention is drawn to the possibility that some of the elements of this document may be the subject of patent rights. OIDF shall not be held responsible for identifying any or all such patent rights.

この文書のいくつかの要素が特許権の対象になる可能性があることに注意が払われている。 OIDFは、かかる特許権の一部または全部を特定する責任を負いません。

Financial API - Part 1: Read Only API Security Profile was prepared by OpenID Foundation Financial API Work Group.

Financial API - 第1部：読み取り専用APIセキュリティプロファイルは、OpenID Foundation Financial API Work Groupによって作成されました。

Financial API consists of the following parts, under the general title Financial Services — Financial API:

Financial APIは、一般的なタイトルFinancial Services - Financial APIの下で、以下の部分で構成されています。

* Part 1: Read Only API Security Profile
* Part 2: Read and Write API Security Profile
* Part 3: Open Data API
* Part 4: Protected Data API and Schema - Read only
* Part 5: Protected Data API and Schema - Read and Write

This part is intended to be used with [RFC6749], [RFC6750], [RFC6736], and [OIDC].

この部分は、[RFC6749]、[RFC6750]、[RFC6736]、および[OIDC]と共に使用することを意図しています。

## Introduction

In many cases, Fintech services such as aggregation services use screen scraping and store user passwords. This model is both brittle and insecure. To cope with the brittleness, it should utilize an API model with structured data and to cope with insecurity, it should utilize a token model such as OAuth [RFC6749, RFC6750].

多くの場合、アグリゲーションサービスなどのFintechのサービスでは、画面スクレイピングとユーザーパスワードの保存が使用されます。 このモデルは壊れやすく、安全でもありません。 脆さに対処するためには、構造化されたデータを持つAPIモデルを利用し、不安に対処するために、OAuth [RFC6749、RFC6750]のようなトークンモデルを利用する必要があります。

Financial API aims to rectify the situation by developing a REST/JSON model protected by OAuth. However, just asking to use OAuth is too vague as there are many implementation choices. OAuth is a framework which can cover wide range of use-cases thus some implementation choices are easy to implement but less secure and some implementation choices are harder to implement but more secure. Financial services on the internet is a use-case that requires more secure implementation choices. That is, OAuth needs to be profiled to be used in the financial use-cases.

Financial APIは、OAuthによって保護されたREST / JSONモデルを開発することによって状況を修正することを目指しています。 しかし、実装の選択肢が多いため、OAuthの使用を尋ねるのはあまりにも曖昧です。 OAuthは、幅広いユースケースをカバーできるフレームワークなので、実装の選択肢は実装が簡単ですがセキュリティは低く、実装の選択肢は実装するのが困難ですが、より安全です。 インターネット上の金融サービスは、より安全な実装の選択を必要とするユースケースです。 つまり、OAuthは、財務的ユースケースで使用するためにプロファイルされる必要があります。

This document is a Part 2 of a set of document that specifies Financial API. It provides a profile of OAuth that is suitable to be used in the write access to the financial data also known as the transactional access. To achieve it, this part of the document specifies the control against such attacks like authorization request tampering, the authorization response tampering including code injection and the state injection, token request phishing, etc. More details are available in the security consideration section.

このドキュメントは、Financial APIを指定する一連のドキュメントの第2部です。 トランザクショナルアクセスとも呼ばれる財務データへの書き込みアクセスに使用するのに適したOAuthのプロファイルを提供します。 これを達成するために、この文書のこの部分では、許可要求改ざん、コードインジェクションと状態注入、トークン要求フィッシングなどを含む認証応答改ざんなどの攻撃に対する制御を規定しています。

## Notational Conventions

The keywords "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in ISO Directive Part 2 [ISODIR2]. These keywords are not used as dictionary terms such that any occurrence of them shall be interpreted as keywords and are not to be interpreted with their natural language meanings.

この文書のキーワード「shall」「shall not」「should」「should」「may」および「can」は、ISO Directive Part 2 [ISODIR2]に記述されているように解釈されるものとします。 これらのキーワードは辞書の用語としては使用されていないため、キーワードとして解釈され、自然言語の意味で解釈されることはありません。

***

## Table of Contents

1.  Scope
2.  Normative references
3.  Terms and definitions
4.  Symbols and Abbreviated terms
5.  Read and Write API Security Profile  
	5.1.  Introduction  
	5.2.  Read and Write API Security Provisions  
        5.2.1.  Introduction  
        5.2.2.  Authorization Server  
        5.2.3.  Public Client  
        5.2.4.  Confidential Client
6.  Accessing Protected Resources (Using tokens)  
    6.1.  Introduction  
    6.2.  Read and write access provisions  
        6.2.1.  Protected resources provisions  
        6.2.2.  Client provisions  
7.  Request object endpoint  
    7.1.  Introduction  
    7.2.  Request  
    7.3.  Successful response  
    7.4.  Error responses  
        7.4.1.  Authorization required  
        7.4.2.  Invalid request  
        7.4.3.  Method Not Allowed  
        7.4.4.  Request entity too large  
        7.4.5.  Too many requests  
8.  Security Considerations  
    8.1.  Introduction  
    8.2.  Uncertainty around the resource server's handling of the access token  
    8.3.  Attacks that involves the weak binding of authorization server endpoints  
        8.3.1.  Introduction  
        8.3.2.  Client credential and authorization code phishing at token endpoint  
        8.3.3.  IdP Mix-up attack  
        8.3.4.  Request object endpoint phishing resistance  
        8.3.5.  Access token phishing  
    8.4.  Attacks that involves the modification of authorization requests and responses  
        8.4.1.  Introduction  
        8.4.2.  Authorization Request parameter injection attack  
        8.4.3.  Authorization Response parameter injection attack  
    8.5.  TLS considerations  
    8.6.  JWS algorithm considerations  
9.  Privacy Considerations
10.  Acknowledgement
11.  Bibliography
§  Authors' Addresses

***


## 1.  Scope

This part of the document specifies the method of

この文書のこの部分は、

applications to obtain the OAuth tokens in an appropriately secure manner for financial data access;
application to utilize OpenID Connect to identify the customer; and
using the tokens to interact with the REST endpoints that provides financial data;
This document is applicable to higher risk use cases which includes commercial and investment banking.

金融データアクセスのために適切に安全な方法でOAuthトークンを取得するアプリケーション
OpenID Connectを利用して顧客を特定するアプリケーション そして
財務データを提供するRESTエンドポイントと相互作用するためにトークンを使用する。
この文書は、商業銀行および投資銀行業務を含むリスクの高い使用例に適用されます。

***

## 2.  Normative references

The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.

以下の参照文書は、この文書の適用に不可欠です。 日付の付いた参考文献については、引用された版のみが適用される。 最新のものがない場合は、改訂版を含む最新版が適用されます。

[ISODIR2] - ISO/IEC Directives Part 2 [ISODIR2]: http://www.iso.org/sites/directives/2016/part2/index.xhtml

[RFC7230] - Hypertext Transfer Protocol -- HTTP/1.1 [RFC7230]: https://tools.ietf.org/html/rfc7230

[RFC6749] - The OAuth 2.0 Authorization Framework [RFC6749]: https://tools.ietf.org/html/rfc6749

[RFC6750] - The OAuth 2.0 Authorization Framework: Bearer Token Usage [RFC6750]: https://tools.ietf.org/html/rfc6750

[RFC7636] - Proof Key for Code Exchange by OAuth Public Clients [RFC7636]: https://tools.ietf.org/html/rfc7636

[RFC5246] - The Transport Layer Security (TLS) Protocol Version 1.2 [RFC5246]: https://tools.ietf.org/html/rfc5246

[RFC6125] - Representation and Verification of Domain-Based Application Service Identity within Internet Public Key Infrastructure Using X.509 (PKIX) Certificates in the Context of Transport Layer Security (TLS) [RFC6125]: https://tools.ietf.org/html/rfc6125

[RFC6819] - OAuth 2.0 Threat Model and Security Considerations [RFC6819]: https://tools.ietf.org/html/rfc6819

[RFC7519] - JSON Web Token (JWT) [RFC7519]:https://tools.ietf.org/html/rfc7519

[BCP195] - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS) [BCP195]: https://tools.ietf.org/html/bcp195

BCP NAPPS - OAuth 2.0 for Native Apps

[OIDC] - OpenID Connect Core 1.0 incorporating errata set 1 [OIDC]: http://openid.net/specs/openid-connect-core-1_0.html

[OIDD] - OpenID Connect Discovery 1.0 incorporating errata set 1 [OIDD]: http://openid.net/specs/openid-connect-discovery-1_0.html

[OIDM] - OAuth 2.0 Multiple Response Type Encoding Practices [OIDM]: http://openid.net/specs/oauth-v2-multiple-response-types-1_0.html

[X.1254] - Entity authentication assurance framework [X.1254]: https://www.itu.int/rec/T-REC-X.1254

[OAUTB] - OAuth 2.0 Token Binding [OAUTB]: https://tools.ietf.org/html/draft-ietf-oauth-token-binding-04

[MTLS] - Mutual TLS Profile for OAuth 2.0 [MTLS]: https://tools.ietf.org/html/draft-ietf-oauth-mtls-02



## 3.  Terms and definitions

For the purpose of this standard, the terms defined in [RFC6749], [RFC6750], [RFC7636], [OpenID Connect Core][OIDC] apply.

この規格の目的上、[RFC6749]、[RFC6750]、[RFC7636]、[OpenID Connect Core] [OIDC]で定義されている用語が適用されます。

## 4.  Symbols and Abbreviated terms

API – Application Programming Interface

CSRF - Cross Site Request Forgery

FAPI - Financial API

FI – Financial Institution

HTTP – Hyper Text Transfer Protocol

OIDF - OpenID Foundation

REST – Representational State Transfer

TLS – Transport Layer Security



## 5.  Read and Write API Security Profile



### 5.1.  Introduction

The OIDF Financial API (FAPI) is a REST API that provides JSON data representing accounts and transactional data. These APIs are protected by the OAuth 2.0 Authorization Framework that consists of [RFC6749], [RFC6750], [RFC7636], and other specifications.

OIDF Financial API（FAPI）は、アカウントとトランザクションデータを表すJSONデータを提供するREST APIです。 これらのAPIは、[RFC6749]、[RFC6750]、[RFC7636]、およびその他の仕様で構成されるOAuth 2.0認証フレームワークによって保護されています。

There are different levels of risks associated with access to these APIs. Read and write access has a higher financial risk than read-only access. As such, the security profiles of the authorization framework protecting these APIs are also different.

これらのAPIへのアクセスには、さまざまなレベルのリスクがあります。 読み取りおよび書き込みアクセスは、読み取り専用アクセスよりも財務上のリスクが高くなります。 したがって、これらのAPIを保護する承認フレームワークのセキュリティプロファイルも異なります。

This profile describes security provisions for the server and client that are appropriate for read and write access by defining the measures to mitigate the attacks that leverage on the weak binding of endpoints in [RFC6749] (e.g. Malicious Endpoints attacks, IdP Mix-up attacks) and attacks that involve modification of the authorization requests and responses that are not protected in [RFC6749] by leveraging on OpenID Connect's Hybrid Flow that returns an ID Token in the authorization response.

このプロファイルは、[RFC6749]（例えば、Malicious Endpoints攻撃、IdP Mix-up攻撃など）のエンドポイントの弱いバインディングを活用する攻撃を緩和するための対策を定義することにより、読み取りと書き込みのアクセスに適したサーバとクライアントのセキュリティ対策を記述しています。 認証レスポンスにIDトークンを返すOpenID Connectのハイブリッドフローを利用して[RFC6749]で保護されていない許可要求と応答の変更を伴う攻撃が含まれます。

While the name ID Token suggests that it is something that provides the identity of the resource owner (subject), it is not necessarily so. While it does identify the authorization server by including the issuer identifier, it is perfectly fine to have ephemeral subject identifier. In this case, the ID Token acts as a detached signature of the issuer to the authorization response and it was an explicit design decision of OpenID Connect Core to make the ID Token act as a detached signature.

名前IDトークンはリソース所有者（サブジェクト）のIDを提供するものであることを示していますが、必ずしもそうであるとは限りません。 発行者識別子を含めることによって認可サーバーを識別しますが、一時的なサブジェクト識別子を持つことはまったく問題ありません。 この場合、IDトークンは発行者の認証応答への切り離された署名として機能し、IDトークンを切り離された署名として動作させるのはOpenID Connect Coreの明示的な設計決定でした。

This document leverages on this fact and protects the authorization response by including the hash of all of the unprotected response parameters, i.e. code and state.

この文書は、この事実を利用して、保護されていないすべての応答パラメータ、つまりコードと状態のハッシュを含めることによって、認証応答を保護します。

While the hash of the code is defined in [OIDC], the hash of the state is not defined. Thus this document defines it as follows.

コードのハッシュは[OIDC]で定義されていますが、状態のハッシュは定義されていません。 したがって、この文書では以下のように定義しています。

** s_hash **

State hash value. Its value is the base64url encoding of the left-most half of the hash of the octets of the ASCII representation of the state value, where the hash algorithm used is the hash algorithm used in the alg Header Parameter of the ID Token's JOSE Header. For instance, if the alg is HS512, hash the state value with SHA-512, then take the left-most 256 bits and base64url encode them. The s_hash value is a case sensitive string.

状態ハッシュ値。 その値は、状態値のASCII表現のオクテットのハッシュの左端の半分のbase64urlエンコーディングであり、使用されるハッシュアルゴリズムはIDトークンのJOSEヘッダーのalgヘッダーパラメーターで使用されるハッシュアルゴリズムです。 たとえば、algがHS512の場合、SHA-512で状態値をハッシュし、次に左端の256ビットを取り、base64urlでそれらをエンコードします。 s_hash値は、大文字と小文字を区別する文字列です。

### 5.2.  Read and Write API Security Provisions



#### 5.2.1.  Introduction

Read and Write Access carries high financial risk, so the protection level is higher than Read-Only Access.

読み取りと書き込みアクセスは高い財務リスクを伴うため、保護レベルは読み取り専用アクセスよりも高くなります。

As a profile of The OAuth 2.0 Authorization Framework, this document mandates the following for the Read and Write API of the FAPI.

OAuth 2.0認証フレームワークのプロファイルとして、このドキュメントでは、FAPIの読み取りAPIと書き込みAPIについて次のことを要求しています。

#### 5.2.2.  Authorization Server

The Authorization Server shall support the provisions specified in clause 5.2.2 of Financial API - Part 1: Read Only API Security Profile.

認証サーバーは、Financial API - 第1部：Read Only API Security Profileの5.2.2項に規定された規定をサポートしなければならない。

In addition, the Authorization server, for the write operation,

さらに、書き込み操作のためのAuthorizationサーバーは、

	1. shall require the request or request_uri parameter to be passed as a JWS signed JWT as in clause 6 of [OIDC];  
	2. shall require the response_type values code id_token or code id_token token;  
	3. shall return ID Token as a detached signature to the authorization response;  
	4. shall include state hash, s_hash, in the ID Token to protect the state value;  
	5. shall only issue holder of key authorization code, access token, and refresh token for write operations;  
	6. shall support [OAUTB] or [MTLS] as a holder of key mechanism;  
	7. shall support user authentication at LoA 3 or greater as defined in [X.1254];  
	8. shall support signed ID Tokens; and  
	9. should support signed and encrypted ID Token.  

	1. [OIDC]の第6項のようにJWS署名JWTとして要求またはrequest_uriパラメータを渡す必要があります。  
	2. response_type値code id_tokenまたはコードid_tokenトークンが必要です。  
	3. IDトークンを拒否された署名として認証応答に返す。  
	4. 状態値を保護するためにIDトークンに状態ハッシュ、s_hashを含める。  
	5. 書き込み操作のためにキー認証コード、アクセストークン、リフレッシュトークンの所有者のみを発行しなければならない。  
	6. キーメカニズムの保持者として[OAUTB]または[MTLS]をサポートしなければならない。  
	7. [X.1254]で定義されているLoA 3以上のユーザ認証をサポートしなければならない。  
	8. 署名付きIDトークンをサポートしなければならない。 そして  
	9. 署名付きで暗号化されたIDトークンをサポートする必要があります。


#### 5.2.3.  Public Client

A Public Client shall support the provisions specified in clause 5.2.3 of Financial API - Part 1: Read Only API Security Profile.

公開クライアントは、Financial API - Part 1：Read Only API Security Profileの5.2.3項に規定された規定をサポートしなければならない。

In addition, the Public Client

	1. shall support [OAUTB] as a holder of key mechanism;  
	2.shall include the request or request_uri parameter as defined in Section 6 of [OIDC] in the authentication request;  
	3. shall request user authentication at LoA 3 or greater by requesting the acr claim as an essential claim as defined in section 5.5.1.1 of [OIDC];  
	4. shall require JWS signed ID Token be returned from endpoints;  
	5. shall verify that the acr claim in an ID Token indicates that user authentication was performed at LoA3 or greater;  
	6. shall verify that the amr claim in an ID Token contains values appropriate for the LoA indicated by the acr claim;  
	7. shall verify that the authorization response was not tampered using ID Token as the detached signature

for write operations.  

	1. キーメカニズムの保持者として[OAUTB]をサポートしなければならない。  
	2. 認証リクエストに[OIDC]のセクション6で定義されているようなrequestまたはrequ_uriパラメータを含まなければならない。  
	3. [OIDC]のセクション5.5.1.1に定義されている必須クレームとしてACRクレームを要求することによりLoA 3以上でのユーザ認証を要求しなければならない。  
	5. JWSが署名したIDトークンがエンドポイントから返されることを要求するものとする。  
	6. IDトークン内のACRクレームが、ユーザ認証がLoA3以上で実行されたことを示すことを検証しなければならない。  
	7. IDトークン内のamrクレームが、acrクレームによって示されるLoAに適切な値を含むことを検証しなければならない。
	8. 承認応答が、分離された署名としてIDトークンを使用して改ざんされていないことを検証しなければならない
書き込み操作のために。


To verify that the authorization response was not tampered using ID Token as the detached signature, the client shall verify that s_hash value is equal to the value calculated from the state value in the authorization response in addition to all the requirements in 3.3.2.12 of [OIDC].

IDトークンを分離署名として使用して認証応答が改ざんされていないことを検証するために、クライアントは、s_hash値が[3.3.2.12]のすべての要件に加えて、認証応答の状態値から計算された値と等しいことを検証しなければならない OIDC]。


#### 5.2.4.  Confidential Client

In addition to the provision to the Public Client and the provisions of clause 5.2.3 , with the exception of OAUTB as the only holder of key mechanism, the Confidential Client

//NG

パブリッククライアントへの規定と5.2.3項の規定に加えて、主要な機構の唯一の保有者であるOAUTBを除き、Confidential Client

	1. shall support [OAUTB] or [MTLS] as a holder of key mechanism;
	2. should require both JWS signed and JWE encrypted ID Tokens to be returned from endpoints

for write operations.

キーメカニズムの保持者として[OAUTB]または[MTLS]をサポートしなければならない。
エンドポイントから返されるJWS署名付きトークンとJWE暗号化IDトークンの両方が必要です
書き込み操作のために。

## 6.  Accessing Protected Resources (Using tokens)



### 6.1.  Introduction

The FAPI endpoints are OAuth 2.0 protected resource endpoints that return various financial information for the resource owner associated with the submitted access token.

FAPIエンドポイントは、送信されたアクセストークンに関連付けられたリソース所有者のさまざまな金融情報を返すOAuth 2.0保護リソースエンドポイントです。

### 6.2.  Read and write access provisions



#### 6.2.1.  Protected resources provisions

The protected resources supporting this document

	1. shall support the provisions specified in clause 6.2.1 Financial API - Part 1: Read Only API Security Profile;
	2. shall adhere to the requirements in [MTLS] or [OAUTB].

	1. 6.2.1金融API - 第1部：読み取り専用APIセキュリティプロファイルに規定された規定をサポートするものとする。
	2. [MTLS]または[OAUTB]の要件を遵守しなければならない。

#### 6.2.2.  Client provisions

The client supporting this document shall support the provisions specified in clause 6.2.2 of Financial API - Part 1: Read Only API Security Profile.

このドキュメントをサポートするクライアントは、Financial API - 第1部：Read Only API Security Profileの6.2.2節で規定された規定をサポートするものとします。

## 7.  Request object endpoint



### 7.1.  Introduction

The client may not want to send the request object by value, either because it is too large, or because it contains sensitive data and the client doesn't want to encrypt the request object. In such cases it is possible to send the request object by reference using a request_uri.

クライアントは、値が大きすぎるか、機密データが含まれており、クライアントが要求オブジェクトを暗号化したくないために、要求オブジェクトを値で送信したくない場合があります。 このような場合、request_uriを使用して参照オブジェクトを要求によって送信することができます。

Note that request_uri can be either URL or URN. If it is a URL, it shall be based on a cryptographic random value so that it is difficult to predict for the attacker.

request_uriは、URLまたはURNのいずれかです。 それがURLの場合、攻撃者を予測するのが難しいように暗号ランダム値に基づいていなければならない。

The request URI can be hosted by the client or by the authorization server. The advantage of the authorization server hosting the request object is that it doesn't have to support outbound requests to a client specified request URI nor rely on the entropy of the URI for the confidentiality of the request object.

要求URIは、クライアントまたは許可サーバーによってホストされます。 要求オブジェクトをホストする認可サーバーの利点は、クライアントが指定した要求URIへの送信要求をサポートする必要もなく、要求オブジェクトの機密性のためにURIのエントロピーに依存しないことです。

When the request object is stored at the authorization server, the request_uri value typically is a URN.

要求オブジェクトが許可サーバーに保管されるとき、request_uri値は通常URNです。

This section defines the specification for the authorization server to provide an endpoint for a client to exchange a request object for a request URI.

このセクションは、要求URIの要求オブジェクトを交換するクライアントのエンドポイントを提供するための許可サーバーの仕様を定義します。

### 7.2.  Request

The request object endpoint is a RESTful API endpoint at the authorization server that accepts a signed request object as an HTTPS POST payload. The request object needs to be signed for the client authentication and as the evidence of the client submitting the request object, which sometimes is called 'non-repudiation'.

要求オブジェクト・エンドポイントは、HTTPS POSTペイロードとして署名付き要求オブジェクトを受け入れる承認サーバーのRESTful APIエンドポイントです。 要求オブジェクトは、クライアント認証と、要求オブジェクトを送信するクライアントの証拠として署名する必要があります。これは、「否認防止」と呼ばれることもあります。

The following is an example of such a request.  

```
POST https://as.example.com/ros/ HTTP/1.1
Host: as.example.com
Content-Type: application/jws
Content-Length: 1288

eyJhbGciOiJSUzI1NiIsImtpZCI6ImsyYmRjIn0.ew0KICJpc3MiOiA
(... abbreviated for brevity ...)
zCYIb_NMXvtTIVc1jpspnTSD7xMbpL-2QgwUsAlMGzw
```

### 7.3.  Successful response

The authorization server shall verify that the request object is valid, the signature algorithm is not none, and the signature is correct as in clause 6.3 of [OIDC].

認証サーバは、要求オブジェクトが有効であり、署名アルゴリズムがnoneではなく、署名が[OIDC]の6.3項のように正しいことを検証しなければならない。

If the verification is successful, the server shall generate a request URI and return a JSON payload that contains request_uri, aud, iss, and exp claims at the top level with 201 Created HTTP response code.

検証が成功した場合、サーバーは要求URIを生成し、request_uri、aud、iss、およびexpのクレームを含むJSONペイロードをトップレベルで201 Created HTTP応答コードで返します。

The value of these claims in the JSON payload shall be as follows: 

JSONペイロードのこれらのクレームの価値は、次のとおりです。

	* request_uri : The request URI corresponding to the request object posted.
	* aud : A JSON string that represents the client identifier of the client that posted the request object.
	* iss : A JSON string that represents the issuer identifier of the authorization server as defined in [RFC7519]. When a pure OAuth 2.0 is used, the value is the redirection URI. When OpenID Connect is used, the value is the issuer value of the authorization server.
	* exp : A JSON number that represents the expiry time of the request URI as defined in [RFC7519].

The following is an example of such a response.

```
HTTP/1.1 201 Created
Date: Tue, 2 May 2017 15:22:31 GMT
Content-Type: application/json

{
    'iss':'https://as.example.com/',
    'aud':'s6BhdRkqt3',
    'request_uri':'urn:example:MTAyODAK',
    'exp':1493738581
}

```

The request URI shall be bound to the client identifier of the client that posted the request object. Since the request URI can be replayed, its lifetime should be short and preferably one-time use.

要求URIは、要求オブジェクトを掲示したクライアントのクライアント識別子に結合されなければならない。 要求URIは再生することができるので、その存続期間は短く、好ましくは一回限りであるべきである。

### 7.4.  Error responses



#### 7.4.1.  Authorization required

If the signature validation fails, the authorization server shall return 401 Unauthorized HTTP error response.

署名の検証が失敗した場合、認証サーバーは401 Unauthorized HTTP error responseを返します。

#### 7.4.2.  Invalid request

If the request object received is invalid, the authorization server shall return 400 Bad Request HTTP error response.

受信した要求オブジェクトが無効である場合、認証サーバーは400 Bad Request HTTPエラー応答を返します。

#### 7.4.3.  Method Not Allowed

If the request did not use POST, the authorization server shall return 405 Method Not Allowed HTTP error response.

要求がPOSTを使用しなかった場合、許可サーバーは405 Method Not Allowed HTTPエラー応答を返します。

#### 7.4.4.  Request entity too large

If the request size was beyond the upper bound that the authorization server allows, the authorization server shall return a 413 Request Entity Too Large HTTP error response.

要求サイズが許可サーバーが許す上限を超えている場合、許可サーバーは413 Request Entity Too Large HTTPエラー応答を返さなければならない。

#### 7.4.5.  Too many requests

If the request from the client per a time period goes beyond the number the authorization server allows, the authorization server shall return a 429 Too Many Requests HTTP error response.

ある期間にクライアントからの要求が許可サーバーの許可数を超えた場合、許可サーバーは429個の「多すぎる要求」HTTPエラー応答を戻すものとします。

## 8.  Security Considerations



### 8.1.  Introduction

As a profile of The OAuth 2.0 Authorization Framework, this specification references the security considerations defined in section 10 of [RFC6749], as well as [RFC6819] - OAuth 2.0 Threat Model and Security Considerations, which details various threats and mitigations.

OAuth 2.0認可フレームワークのプロファイルとして、この仕様書は[RFC6749]のセクション10で定義されたセキュリティ考慮事項と、様々な脅威と緩和を詳述する[RFC6819] - OAuth 2.0脅威モデルとセキュリティ考察を参照しています。

### 8.2.  Uncertainty around the resource server's handling of the access token

There is no way that the client can find out whether the resource access was granted for the Bearer token or holder of key token. The two differ in the risk profile and the client may want to differentiate them. The protected resources that conforms to this document shall not accept a plain Bearer token. They shall only support token bound access tokens via [MTLS] or [OAUTB].

ベアラトークンまたはキートークンの所有者に対してリソースアクセスが許可されているかどうかをクライアントが確認できる方法はありません。 2つはリスクプロファイルが異なり、クライアントはそれらを差別化したいかもしれません。 この文書に適合する保護されたリソースは、プレーンベアラトークンを受け入れてはならない。 彼らは、[MTLS]または[OAUTB]を介してのみ、トークンバウンドアクセストークンをサポートしなければならない。

### 8.3.  Attacks that involves the weak binding of authorization server endpoints



#### 8.3.1.  Introduction

In [RFC6749] and [RFC6750], the endpoints that the authorization server offers are not tightly bound together. There is no notion of authorization server identifier (issuer identifier) and it is not indicated in the authorization response unless the client uses different redirection URI per authorization server. While it is assumed in the OAuth model, it is not explicitly spelled out and thus many clients use the same redirection URI for different authorization servers exposing attack surface. Several attacks are identified by now and many of them are explained in more details in [RFC6819] in more detail.

[RFC6749]と[RFC6750]では、認証サーバーが提供するエンドポイントは密接に束縛されていません。 認可サーバー識別子（発行者ID）の概念はなく、クライアントが認可サーバーごとに異なるリダイレクトURIを使用しない限り、認可応答には示されません。 OAuthモデルでは仮定されていますが、明示的にスペルアウトされていないため、多くのクライアントが攻撃サーフェスを公開する異なる認証サーバーに同じリダイレクトURIを使用します。 いくつかの攻撃が今では識別されており、その多くは[RFC6819]でより詳細に説明されています。

#### 8.3.2.  Client credential and authorization code phishing at token endpoint

In this attack, the client developer is social engineered into believing that the token endpoint has changed to the URL that is controlled by the attacker. As the result, the client sends the code and the client secret to the attacker, which will be replayed subsequently.

この攻撃では、クライアントの開発者は、トークンエンドポイントが攻撃者によって制御されたURLに変更されたと信じるようにソーシャルエンジニアリングされます。 その結果、クライアントはコードとクライアントの秘密情報を攻撃者に送信し、攻撃者はその後に再生されます。

When the FAPI client uses [MTLS] or [OAUTB], the authorization code is bound to the TLS channel, any phished client credentials and authorization codes submitted to the token endpoint cannot be used since the authorization code is bound to a particular TLS channel.

FAPIクライアントが[MTLS]または[OAUTB]を使用する場合、認証コードはTLSチャネルにバインドされます。フィッシングされたクライアントクレデンシャルとトークンエンドポイントに送信された認証コードは、認証コードが特定のTLSチャネルにバインドされているため使用できません。

#### 8.3.3.  IdP Mix-up attack

In this attack, the client has registered multiple IdPs and one of them is a rogue IdP that returns the same client_id that belongs to one of the honest IdPs. When a user clicks on a malicious link or visits a compromised site, an authorization request is sent to the rogue Idp. The rogue Idp then redirects the client to the honest IdP that has the same client_id. If the user is already logged on at the honest IdP, then the authentication may be skipped and a code is generated and returned to the client. Since the client was interacting with the rogue IdP, the code is sent to the rogue IdP's token endpoint. At the point, the attacker has a valid code that can be exchanged for an Access Token at the honest IdP.

この攻撃では、クライアントは複数のIdPを登録しています。そのうちの1つは正直なIdPの1つに属する同じclient_idを返す不正なIdPです。 ユーザーが悪質なリンクをクリックしたり、侵害されたサイトにアクセスした場合、不正なIdpに認証要求が送信されます。 次に、不正なIdpは、同じclient_idを持つ正直なIdPにクライアントをリダイレクトします。 ユーザが正直なIdPですでにログオンしている場合、認証はスキップされ、コードが生成されてクライアントに返されます。 クライアントが不正なIdPと対話していたので、コードは不正なIdPのトークンエンドポイントに送信されます。 この時点で、攻撃者は正当なIdPでアクセストークンと交換できる有効なコードを持っています。

This is mitigated by the use of Hybrid flow in which the Honest IdP's issuer identifier is included as the value of iss. The client then sends the code to the token endpoint that is associated with the issuer identifier thus it will not get to the attacker.

これは、Honest IdPの発行者識別子がissの値として含まれるハイブリッドフローの使用によって軽減されます。 クライアントは、コードを発行者識別子に関連付けられたトークンエンドポイントに送信します。したがって、攻撃者には届きません。

#### 8.3.4.  Request object endpoint phishing resistance

An attacker can use social engineering to have the administrator of the client set the request object endpoint to a URL under the attacker's control. In this case, sensitive information included in the request object will be revealed to the attacker. To prevent this, the authorization server should communicate to the client developer the proper change process repeatedly to help client developers to be less susceptible to such social engineering.

攻撃者はソーシャルエンジニアリングを使用して、クライアントの管理者に要求オブジェクトのエンドポイントを攻撃者の制御下のURLに設定させることができます。 この場合、要求オブジェクトに含まれる機密情報が攻撃者に公開されます。 これを防ぐために、認可サーバーは、クライアント開発者がそのようなソーシャルエンジニアリングの影響を受けにくくなるように、適切な変更プロセスを繰り返しクライアント開発者に伝える必要があります。

#### 8.3.5.  Access token phishing

When the FAPI client uses [MTLS] or [OAUTB], the access token is bound to the TLS channel, it is access token phishing resistant as the phished access tokens cannot be used.

FAPIクライアントが[MTLS]または[OAUTB]を使用する場合、アクセストークンはTLSチャネルにバインドされます。フィッシングされたアクセストークンを使用できないため、アクセストークンはフィッシング耐性です。

### 8.4.  Attacks that involves the modification of authorization requests and responses



#### 8.4.1.  Introduction

In [RFC6749] the authorization request and responses are not integrity protected. Thus, an attacker can modify them.

[RFC6749]では、認証要求と応答は完全性保護されていません。 したがって、攻撃者はそれらを変更することができます。

#### 8.4.2.  Authorization Request parameter injection attack

In [RFC6749], the authorization request is sent as query parameter. Although [RFC6749] mandates the user of TLS, the TLS is terminated in the browser and thus not protected within the browser. Leveraging on it, an attacker can tamper the authorization request and insert his own parameter values.

[RFC6749]では、認証要求がクエリパラメータとして送信されます。 [RFC6749]はTLSのユーザを義務づけているが、TLSはブラウザで終了し、ブラウザ内で保護されていない。 これを利用することで、攻撃者は認証要求を改ざんして自分のパラメータ値を挿入することができます。

Attacks like Malicious Endpoint Attack requires this property to succeed.

Malicious Endpoint Attackのような攻撃では、このプロパティが成功する必要があります。

The use of a request object or request_uri in the authorization request will prevent tampering with the request parameters.

承認要求に要求オブジェクトまたはrequest_uriを使用すると、要求パラメータの改ざんを防止できます。  

IdP confusion attack reported in [SoK: Single Sign-On Security – An Evaluation of OpenID Connect](https://www.nds.rub.de/media/ei/veroeffentlichungen/2017/01/30/oidc-security.pdf) is this kind of attack.

SoKで報告されたIdP混乱攻撃：シングルサインオンセキュリティ - OpenID Connectの評価は、この種の攻撃です。


#### 8.4.3.  Authorization Response parameter injection attack

This attack occurs when the victim and attacker use the same relying party client. The attacker is somehow able to capture the authorization code and state from the victim's authorization response and uses them in his own authorization response.

この攻撃は、被害者と攻撃者が同じ信頼関係のクライアントを使用している場合に発生します。 攻撃者は、犠牲者の認証応答から何らかの形で認証コードと状態を取得し、自身の認証応答でそれらを使用することができます。

This can be mitigated by using hybrid flow where the c_hash, at_hash, and s_hash can be used to verify the validity of the authorization code, access token, and state parameters. The server can verify that the state is the same as what was stored in the browser session at the time of the authorization request.

これは、c_hash、at_hash、およびs_hashを使用して、認証コード、アクセストークン、および状態パラメータの有効性を検証するために使用できるハイブリッドフローを使用することによって軽減できます。 サーバーは、認証要求の時点でブラウザセッションに格納された状態と同じ状態であることを確認できます。

### 8.5.  TLS considerations

As confidential information is being exchanged, all interactions shall be encrypted with TLS (HTTPS).

秘密情報が交換されると、すべての相互作用はTLS（HTTPS）で暗号化されます。

The recommendations for Secure Use of Transport Layer Security in BCP195 shall be followed, with the following additional requirements:

BCP195のトランスポート層セキュリティの安全な使用に関する推奨事項に従わなければならず、以下の追加要件が必要となる。

	1. Only the following 4 cipher suites shall be permitted:
		* TLS_DHE_RSA_WITH_AES_128_GCM_SHA256
		* TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
		* TLS_DHE_RSA_WITH_AES_256_GCM_SHA384
		* TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
	2. TLS version 1.2 or later shall be used for all communications.
	3. A TLS server certificate check shall be performed, as per [RFC6125].


### 8.6.  JWS algorithm considerations

JWS signatures shall use the PS256 or ES256 algorithms for signing.

JWS署名は、署名にPS256またはES256アルゴリズムを使用するものとする。

## 9.  Privacy Considerations

If the client is to be used by a single user, the client certificate will provide the means for the websites that belong to different administrative domains to collude and correlate the user's access. For this reason, public clients that reside on a user's terminal should avoid [MTLS] and use [OAUTB] instead.  
When claims related to the subject are returned in the ID Token in the front channel, implementations should consider encrypting the ID Token to lower the risk of personal information disclosure.

クライアントが単一のユーザーによって使用される場合、クライアント証明書は、異なる管理ドメインに属するWebサイトに、ユーザーのアクセスを結集して関連付ける手段を提供します。 このため、ユーザーの端末に常駐するパブリッククライアントは[MTLS]を回避し、代わりに[OAUTB]を使用する必要があります。  
サブジェクトに関連するクレームがフロントチャネルのIDトークンに返される場合、実装は個人情報開示のリスクを低くするためにIDトークンを暗号化することを検討する必要があります。

## 10.  Acknowledgement

Following people contributed heavily towards this document.

Nat Sakimura (Nomura Research Institute) -- Chair, Editor  
Anoop Saxana (Intuit) -- Co-chair, FS-ISAC Liaison  
Anthony Nadalin (Microsoft) -- Co-chair, SC 27 Liaison  
Edmund Jay (Illumila) -- Co-editor  
Dave Tonge (Momentum Financial Technology) -- UK Implementation Entity Liaison  
Paul A. Grassi (NIST) -- X9 Liaison  
Joseph Heenan (Authlete)  
Sascha H. Preibisch (CA)  
John Bradley (Ping Identity)  
Henrik Bearing (Peercraft)  
Tom Jones (Independent)  
Axel Nenker (deutsche telekom)  
Torsten Lodderstedt (YES)  
Ralph Bragg (Raidiam)  


## 11.  Bibliography

[OFX2.2] Open Financial Exchange 2.2  
[HTML4.01] “HTML 4.01 Specification,” World Wide Web Consortium   Recommendation REC-html401-19991224, December 1999  
[RFC7662] OAuth 2.0 Token Introspection  
[DDA] Durable Data API, (2015), FS-ISAC  
[SoK] Mainka, C., Mladenov, V., Schwenk, J., and T. Wich: SoK: Single Sign-On Security – An Evaluation of OpenID Connect  


Authors' Addresses

 	Nat Sakimura
 	Nomura Research Institute, Ltd.
Email: 	n-sakimura@nri.co.jp
URI: 	http://nat.sakimura.org/
 	 
 	John Bradley
 	Ping Identity
Email: 	ve7jtb@ve7jtb.com
URI: 	http://www.thread-safe.com/
 	 
 	Edmund Jay
 	Illumila
Email: 	ejay@mgi1.com
URI: 	http://illumi.la/