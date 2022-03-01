# Lab 2: JAN RUIBAR

### 2-bit comparator

1. Karnaugh maps for other two functions:

   Greater than:

   ![K-maps](https://i.imgur.com/VRaYkzV.png)

   Less than:

   ![K-maps](https://i.imgur.com/fpaHOIy.png)

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

   ![Logic functions](https://i.imgur.com/a5lWC4H.png)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **xxxx19**

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

		-- First test case
        s_b <= "0001"; -- Such as "0001" if ID = xxxx19
        s_a <= "1001";        -- Such as "1001" if ID = xxxx19
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 0001, 1001 FAILED" severity error;


        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait; -- Data generation process is suspended forever
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![your figure](https://i.imgur.com/1cWBlF1.png)

3. Link to your public EDA Playground example:

   [https://www.edaplayground.com/x/8PqF](https://www.edaplayground.com/x/8PqF)
