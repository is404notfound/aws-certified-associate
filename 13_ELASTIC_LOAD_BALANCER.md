# Elastic Load Balancer (ELB)

1. **로드밸런싱**
- 로드밸런싱은 여러 인스턴스로 트래픽을 분배하는 기술로, 주로 안정적인 서비스 운영을 위해 사용됩니다. 특히 오토 스케일링을 활용하여 서비스의 확장을 자동으로 처리하는 방식이 일반적입니다. 하지만 이 방식에는 몇 가지 단점이 있습니다.

- 여러 인스턴스의 IP 주소 문제: 오토 스케일링을 통해 인스턴스 수를 동적으로 확장하더라도, 사용자는 각 인스턴스의 IP 주소를 알고 있어야 합니다. 이는 관리 및 유지보수에 어려움을 줄 수 있습니다.

하나의 인스턴스에 유저가 몰리는 문제: 만약 하나의 인스턴스에 너무 많은 유저가 몰리면, 해당 인스턴스의 처리 능력을 초과하게 되어 서비스 성능이 저하될 수 있습니다. 이때, 로드밸런싱을 통해 트래픽을 적절히 분배하지 않으면, 특정 인스턴스가 과부하 상태에 빠지거나 서버 다운과 같은 문제가 발생할 수 있습니다.

결론적으로, 오토 스케일링 그룹은 매우 유용하지만, 로드밸런싱이 없다면 인스턴스들 간의 트래픽 분배가 제대로 이루어지지 않아 안정적인 서비스 제공이 어려울 수 있습니다.

---

2. **엘라스틱 로드 밸런서** (ELB)
Elastic Load Balancing (ELB)는 AWS에서 제공하는 로드밸런싱 서비스로, 사용자의 트래픽을 여러 인스턴스에 효율적으로 분배하는 역할을 합니다.

- 트래픽 경로 통합: ELB는 다수의 유저 트래픽을 하나의 경로로 묶어서 관리합니다. 이를 통해 사용자는 별도의 인스턴스 IP를 알 필요 없이, ELB에 접속하면 자동으로 트래픽이 적절한 인스턴스로 분배됩니다.

- 트래픽 분산: ELB는 유입된 트래픽을 여러 인스턴스로 균등하게 분배하여, 각 인스턴스의 부하를 최소화하고, 서비스의 가용성과 성능을 향상시킵니다.