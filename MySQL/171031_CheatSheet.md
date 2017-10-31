# CheatSheet

```
# 데이터베이스 생성
CREATE DATABASE TEST1 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

# 사용자 생성
CREATE USER TEST1;

# 데이터베이스에 대한 모든 권한 부여
GRANT ALL PRIVILEGES ON TEST1.* TO 'TEST1'@'localhost' IDENTIFIED BY 'TEST1';

# 테이블 생성
CREATE TABLE `test_table` (
  `client_id` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `datetime` datetime NOT NULL,
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci
PARTITION BY RANGE(TO_DAYS(`datetime`)) (
    PARTITION P20171018 VALUES LESS THAN (TO_DAYS('2017-10-19')),
    PARTITION P_MAX VALUES LESS THAN (MAXVALUE)
);

# 파티션 분할
ALTER TABLE `test_table` REORGANIZE PARTITION P_MAX INTO (
    PARTITION P20171025 VALUES LESS THAN (TO_DAYS('2017-10-26')),
    PARTITION P_MAX VALUES LESS THAN (MAXVALUE)
);


# 파티션 삭제
ALTER TABLE test_table DROP PARTITION P20171019

# 기본 테이블에 파티션 적용
ALTER TABLE `test_table` PARTITION BY RANGE(TO_DAYS(`datetime`)) (
    PARTITION P20171025 VALUES LESS THAN (TO_DAYS('2017-10-26')),
    PARTITION P_MAX VALUES LESS THAN (MAXVALUE)
);

# 파티션 조회
SELECT PARTITION_ORDINAL_POSITION, PARTITION_NAME, TABLE_ROWS, PARTITION_METHOD 
FROM information_schema.PARTITIONS
WHERE TABLE_SCHEMA = 'TEST1' AND TABLE_NAME = 'test_table';

# 인덱스 추가
CREATE INDEX test_table_datetime_ix ON test_table(`datetime`);

ALTER TABLE test_table ADD INDEX test_table_datetime_ix (`datetime`);

# 인덱스 확인
SHOW INDEX FROM test_table;

# 테이블 인코딩 설정
ALTER TABLE tablename CONVERT TO CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
