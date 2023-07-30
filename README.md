# ir-national-code
Validation of Iran's national code

def test_national_code(code):
    code=str(code)
    if not(code.isnumeric()) or len(code)!=10 or code=="0000000000":
        return False
    else:
        Sum=0
        for i in range (0,9):
            Sum+=int(code[i])*(10-i)
        if Sum%11<2 and int(Sum%11)==int(code[9]):
            return True
        elif int(11-(Sum%11))==int(code[9]):
            return True
        else :return False
