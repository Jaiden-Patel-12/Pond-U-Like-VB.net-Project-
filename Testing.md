# Testing

The following tests were carried out to ensure the application functioned correctly and the calculations were calculated as expected. 
The original testing document contained screenshots for each test showing before and after to verify that each test was either successful or unsuccessful. 

| Test No. | Test | Expected Result | Actual Result | Status |
|----------|------|-----------------|---------------|:------:|
| 1 | Erroneous Length Input | Error message displayed and input rejected. | Error message displayed and textbox cleared. | ✅ |
| 2 | Extreme Length Input | Maximum valid length accepted. | Input accepted successfully. | ✅ |
| 3 | Normal Length Input | Input accepted without errors. | Input accepted successfully. | ✅ |
| 4 | Erroneous Width Input | Error message displayed and input rejected. | Error message displayed and textbox cleared. | ✅ |
| 5 | Extreme Width Input | Maximum valid width accepted. | Input accepted successfully. | ✅ |
| 6 | Normal Width Input | Input accepted without errors. | Input accepted successfully. | ✅ |
| 7 | Erroneous Depth Input | Error message displayed and input rejected. | Error message displayed and textbox cleared. | ✅ |
| 8 | Extreme Depth Input | Maximum valid depth accepted. | Input accepted successfully. | ✅ |
| 9 | Normal Depth Input | Input accepted without errors. | Input accepted successfully. | ✅ |
| 10 | Correct Liner Cost | Correct liner cost calculated. | Correct cost displayed. | ✅ |
| 11 | Correct Gauge Type | Correct liner gauge displayed. | Correct gauge displayed. | ✅ |
| 12 | Time Display | Current time shown and updated automatically. | Worked correctly. | ✅ |
| 13 | Date Display | Current date displayed correctly. | Worked correctly. | ✅ |
| 14 | Save Customer Reference | Reference saved to Order.txt. | Saved successfully. | ✅ |
| 15 | Save Customer Name | Name saved to Order.txt. | Saved successfully. | ✅ |
| 16 | Save Cost | Cost saved to Order.txt. | Saved successfully. | ✅ |
| 17 | Save Gauge Type | Gauge type saved to Order.txt. | Saved successfully. | ✅ |
| 18 | Save Area | Area saved to Order.txt. | Saved successfully. | ✅ |
| 19 | View Saved Data | Saved records displayed in application. | Displayed correctly. | ✅ |
| 20 | Quit Button | Application closes. | Closed successfully. | ✅ |
| 21 | Calculate Button | Validation, calculations and outputs performed correctly. | Worked correctly. | ✅ |

## Summary

All planned tests passed successfully.

Testing confirmed:

- Input validation works correctly.
- Pond liner calculations are accurate.
- The correct liner gauge is selected.
- Cost calculations are accurate.
- Customer records are successfully saved.
- Saved records can be viewed.
- Date and time display correctly.
- All application buttons perform as expected.
