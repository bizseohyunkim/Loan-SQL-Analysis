Loan Data SQL Analysis | Credit Risk Focus
SQL(SQLite) 및 Python 기반 대출 데이터 전처리 및 연체 위험군 분석

본 프로젝트는 비즈니스 도메인 지식을 바탕으로 SQL과 Python을 연계하여 금융 데이터를 체계적으로 관리하고, 다각도의 집계 및 필터링 쿼리를 통해 부도 위험이 높은 고객 세그먼트를 도출하는 것을 목적으로 합니다.

프로젝트 개요 | Overview
기존 머신러닝 모델링 프로젝트와 연계하여, 실제 데이터베이스 환경(Relational Database)에서 SQL을 활용해 데이터를 정규화하고 비즈니스 관점의 핵심 지표를 추출하는 과정을 구현했습니다. 특히 저신용군 및 고위험 고객군에 대한 복합 필터링을 통해 리스크 관리 인사이트를 도출했습니다.

사용 기술 | Tech Stack
Database: SQLite (Relational Database Modeling & Management)

Analysis: Python, Pandas (SQL-to-DataFrame Pipeline 구축)

Visualization: Matplotlib (신용 등급 및 소득 구간별 부도율 시각화)

Version Control: Git / GitHub

분석 과정 | Process
1단계 | 데이터베이스 모델링 및 구축
Normalization: customers와 loans 테이블로 데이터를 분리 및 정규화하여 데이터 무결성 확보

Data Integration: Python을 활용하여 원천 CSV 데이터를 SQLite DB 내 각 테이블로 삽입 및 관리

2단계 | SQL 기반 핵심 지표 분석
Default Rate by Grade: 신용 등급(A~G)에 따른 부도율 및 평균 이자율 산출을 통해 등급 체계의 유효성 검증

Income Segment Analysis: 고객 소득 구간별 대출 비중 분석 및 상환 능력 지표 파악

Loan Intent Analysis: 대출 목적별 부도율 비교를 통한 고위험 목적군 식별

3단계 | 고위험 고객 추출 (High-Risk Filtering)
Criteria: 아래 조건을 동시 충족하는 초고위험군 고객 20명 추출

신용 등급 D~G (저신용군)

대출 이자율 15% 초과 및 소득 대비 대출 비중(DTI) 30% 초과

과거 부도 이력 보유 (Default History: 'Y')

결론 | Conclusion
Credit Risk Logic: 신용 등급이 낮아질수록 부도율이 비선형적으로 급증함을 확인하여 최저 등급(G등급)에 대한 심사 강화 필요성 도출

Income & Default Correlation: 연 소득 3만 달러 미만 저소득층의 부도율이 가장 높게 나타나며, 소득 수준과 상환 안정성 간의 양의 상관관계 확인

Strategic Suggestion: 과거 부도 이력이 있는 저신용군 중 DTI가 높은 고객군을 집중 모니터링 대상으로 선정하는 리스크 필터링 시스템 제안

프로젝트 구조 | Project Structure
01_create_tables.ipynb: DB 연결, 테이블 스키마 설계 및 데이터 삽입 과정

02_analysis.ipynb: 핵심 SQL 쿼리 실행 및 시각화 인사이트 도출

images/: 분석 결과 시각화 차트 (PNG 형식)
