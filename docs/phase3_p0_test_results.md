# Phase 3 P0 Automated Test Results

- Timestamp (UTC): 2026-04-05 07:08:38
- Total tests: 40
- Passed: 40
- Failed: 0

| Test ID | Scenario | Result | Details |
|---|---|---|---|
| T1.1 | FraudShield page loads within 15s | ✅ PASS | status=200, load_ms=349.2 |
| T1.2 | FraudShield sample data auto-loaded | ✅ PASS | collection_count=6 |
| T1.3 | FraudShield suggestion chips configured | ✅ PASS | checked demo/app.py for SAMPLE_QUESTIONS + chat input |
| T1.4 | FraudShield suggestion-like query returns answer+sources | ✅ PASS | status=200, sources=3 |
| T1.5 | FraudShield follow-up query returns contextual response | ✅ PASS | status=200, answer_len=2946 |
| T1.6 | FraudShield upload+ingest succeeds | ✅ PASS | status=200, chunks_created=1 |
| T1.7 | FraudShield irrelevant question handled gracefully | ✅ PASS | status=200, answer_preview=As FraudShield, I must inform you that the provided context documents do not contain any relevant information regarding  |
| T1.8 | FraudShield API status connected | ✅ PASS | status=healthy, qdrant_connected=True |
| T2.1 | MedicaidGuard page loads within 15s | ✅ PASS | status=200, load_ms=318.2 |
| T2.2 | Normal claim -> LOW risk | ✅ PASS | status=200, risk=LOW, p=0.227371 |
| T2.3 | Suspicious scenario -> MEDIUM/HIGH risk | ✅ PASS | status=200, risk=MEDIUM, p=0.482602 |
| T2.4 | Likely fraud -> HIGH/CRITICAL and p>0.7 | ✅ PASS | status=200, risk=CRITICAL, p=0.993423 |
| T2.5 | Risk factors present | ✅ PASS | risk_factors=3 |
| T2.6 | Inference time <100ms | ✅ PASS | inference_time_ms=0.264 |
| T2.7 | Batch sample works | ✅ PASS | status=200, batch_size=100 |
| T2.8 | Batch distribution data available | ✅ PASS | predictions=100 |
| T2.9 | Batch flagged transactions metric available | ✅ PASS | fraud_count=62 |
| T2.10 | Model info tab contains AUPRC 0.8379 | ✅ PASS | checked demo/app.py static model tab text |
| T3.1 | Agent Monitor page loads within 15s | ✅ PASS | status=200, load_ms=283.4 |
| T3.2 | Suspicious wire executes agents with timing | ✅ PASS | status=200, trace_len=4 |
| T3.3 | Suspicious wire risk is elevated | ✅ PASS | risk=CRITICAL |
| T3.4 | Pattern detection includes structuring/smurfing | ✅ PASS | patterns=[{'pattern_name': 'Structuring (Smurfing)', 'confidence': 0.99, 'typology': 'smurfing', 'evidence': ['amount_near_threshold', 'velocity_spike']}, {'pattern_name': 'Mule Account Funnel', 'confidence': 0.9133, 'typology': 'mule_account', 'evidence': ['new_receiver', 'velocity_spike']}, {'pattern_name': 'Bust-Out Behavior', 'confidence': 0.8333, 'typology': 'bust_out', 'evidence': ['amount_near_threshold', 'velocity_spike']}, {'pattern_name': 'Identity Fraud Signal', 'confidence': 0.7, 'typology': 'identity_fraud', 'evidence': ['new_receiver']}] |
| T3.5 | SAR report generated | ✅ PASS | report_len=1153 |
| T3.6 | Pipeline trace renders 4+ steps | ✅ PASS | trace_len=4 |
| T3.7 | Normal payment returns low-ish risk | ✅ PASS | risk=LOW |
| T3.8 | LangSmith trace field present in API response | ✅ PASS | langsmith_trace_url=None |
| T4.1 | Fraud LLM page loads within 15s | ✅ PASS | status=200, load_ms=299.3 |
| T4.2 | Example 1 classified FRAUDULENT | ✅ PASS | classification=FRAUDULENT |
| T4.3 | Example 2 classified LEGITIMATE | ✅ PASS | classification=LEGITIMATE |
| T4.4 | Example 3 classified FRAUDULENT/SUSPICIOUS | ✅ PASS | classification=FRAUDULENT |
| T4.5 | Responses include reasoning | ✅ PASS | reasoning_lines=3 |
| T4.6 | Custom input classification works | ✅ PASS | classification=FRAUDULENT |
| TX.1A | FraudShield demo reachable | ✅ PASS | status=200, ms=303.8 |
| TX.3A | No obvious secrets in HTML source | ✅ PASS | leaked=False |
| TX.1B | MedicaidGuard demo reachable | ✅ PASS | status=200, ms=303.3 |
| TX.3B | No obvious secrets in HTML source | ✅ PASS | leaked=False |
| TX.1C | Agent Monitor demo reachable | ✅ PASS | status=200, ms=327.4 |
| TX.3C | No obvious secrets in HTML source | ✅ PASS | leaked=False |
| TX.1D | Fraud LLM demo reachable | ✅ PASS | status=200, ms=192.3 |
| TX.3D | No obvious secrets in HTML source | ✅ PASS | leaked=False |
