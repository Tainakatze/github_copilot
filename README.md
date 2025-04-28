# github_copilot
Objetivo:
Inputando um número de cartão de crédito, validar qual a bandeira daquele cartão.

function validateCreditCard(cardNumber) {
    // Remove spaces and dashes from the card number
    cardNumber = cardNumber.replace(/\s|-/g, '');

    // Visa: Starts with 4
    if (/^4\d{12}(\d{3})?$/.test(cardNumber)) {
        return "Visa";
    }

    // MasterCard: Starts with 51-55 or 2221-2720
    if (/^(5[1-5]\d{14}|2(2[2-9]\d{2}|[3-6]\d{3}|7[0-1]\d{2}|720)\d{12})$/.test(cardNumber)) {
        return "MasterCard";
    }

    // Elo: Matches specific intervals (4011, 4312, 4389, etc.)
    if (/^(4011|4312|4389)\d*$/.test(cardNumber)) {
        return "Elo";
    }

    // American Express: Starts with 34 or 37
    if (/^3[47]\d{13}$/.test(cardNumber)) {
        return "American Express";
    }

    // Discover: Starts with 6011, 65, or 644-649
    if (/^(6011|65|64[4-9])\d*$/.test(cardNumber)) {
        return "Discover";
    }

    // Hipercard: Generally starts with 6062
    if (/^6062\d*$/.test(cardNumber)) {
        return "Hipercard";
    }

    // If no match, return Invalid
    return "Invalid";
}

// Example usage
const cardNumber = "4011 1234 5678 9012";
const flag = validateCreditCard(cardNumber);
console.log(`The card flag is: ${flag}`);
