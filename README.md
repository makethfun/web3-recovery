# 바이낸스 Web3 Wallet 구조 자료 (2026-10-19)

## 키 구조 (MPC, 키 조각 3개 중 2개 필요)
- Share 1: 바이낸스 보관
- Share 2: 사용자 기기에 저장 (기기 캐시 삭제 시 유실 가능 — 공식 FAQ 경고)
- Share 3: 복구 비밀번호로 암호화 → 클라우드(iCloud/Google Drive) 또는 QR 방식 백업
- 니모닉이 없는 구조가 원칙 (공식 글: 조각을 분산 저장하므로 니모닉 불필요)

## 복구 경로
- 기기 분실: Share 3(백업) + Share 1(바이낸스) 조합으로 복구
- QR 백업: Share 3를 Greenfield(탈중앙 클라우드)에 저장하고 QR을 사용자가 보관. QR만 유출돼도 복구 비밀번호 + 바이낸스 계정이 없으면 못 씀
- 복구 비밀번호 분실 시 바이낸스도 복구 불가

## Self custody 전환
- 복구 비밀번호로 키 조각을 암호화해 클라우드/QR로 백업
- 전환 시 바이낸스 조각이 어떻게 되는지는 공식 FAQ에 명시 없음 (미확인)
- 공식: self custody에서는 키 분실 시 "아무도 복구해 줄 수 없음"
- 제3자 리뷰: "Emergency Export"로 개인키 내보내기 가능, 쓰면 바이낸스 지갑은 사용 불가

## 출처
- https://www.binance.com/en/support/faq/how-to-back-up-my-binance-web3-wallet-via-qr-code-53521dedad474c908ec3761a935cb8d6
- https://www.binance.com/en/support/faq/how-to-upgrade-my-binance-web3-wallet-to-self-custody-43026a1992ad4198ae56df6688ad38f4
- https://www.binance.com/en/support/faq/why-do-i-need-to-backup-my-binance-web3-wallet-and-how-to-do-it-4efebcb9a937417ca31baa2f7754c50f
- https://www.binance.com/en/square/post/1678387
- https://www.cypherock.com/blogs/is-binance-web3-wallet-safe
- https://www.financemagnates.com/cryptocurrency/binances-web3-wallet-is-multi-party-computation-the-solution/
