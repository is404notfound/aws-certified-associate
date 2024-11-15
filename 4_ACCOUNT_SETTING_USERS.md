# AWS Account Settings and User

## AWS Account 생성 시

- AWS 계정을 생성하면 root 유저와 기본 리소스(기본 VPC 등)가 자동으로 생성됩니다.
- AWS 계정에는 고유한 아이디(number 형식)가 부여되며, 별명 지정도 가능합니다 (string).

## 루트 유저 (Root User)

- **루트 유저**는 생성된 계정의 모든 권한을 자동으로 가지는 유저입니다.
- 계정 생성 시 입력한 이메일 주소(email address)로 로그인합니다.
- **주의 사항**:
  - 루트 유저는 탈취 시 복구가 매우 어렵기 때문에 사용을 최대한 자제하고, MFA 설정을 필수로 해야 합니다.
  - 루트 유저는 계정 설정 변경이나 빌링 등의 관리 용도로만 사용되며, AWS API 호출이 불가능합니다 (Access Key/Secret Access Key 부여 불가).

## IAM User

- **IAM (Identity and Access Management)**: AWS의 모든 권한을 관리하는 서비스입니다.
- IAM 유저는 IAM을 통해 생성한 유저로, 특정 아이디로 로그인을 해야 합니다 (이메일 X).
- **기본 권한 없음**: IAM 유저는 생성 시 기본 권한이 없으므로 별도로 권한을 부여해야 합니다.
  - 예) 관리자 IAM User, 개발자 IAM User, 디자이너 IAM User, 회계팀 IAM User 등의 세부적인 권한 설정이 가능합니다.
- 사람이 아닌 애플리케이션 등의 가상의 주체를 대표할 수도 있습니다.

### AWS API 호출 기능

- **Access Key**: 아이디 개념 (공개 가능)
- **Secret Access Key**: 패스워드 개념 (공개 불가, 재발급 불가, 변경 불가, 계정 삭제 후 다시 생성해야 합니다).

- AWS의 모든 작업(관리 포함)은 **관리용 IAM User**를 만들어 수행하며, 권한 부여 시 루트 유저처럼 모든 권한을 가질 수 있습니다.
  - 단, 빌링 관련 권한은 루트 유저가 별도로 허용해야 합니다.

## AWS 계정 생성 요약

- 최초 이메일 계정 생성 시, root 유저가 생성되며, root user 하위로 IAM 서비스를 사용할 권한과 각 리전별 관리할 수 있는 서비스 권한이 부여됩니다.
